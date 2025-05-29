<script>
  import { getContext, onDestroy } from "svelte";
  import { CellIcon, SuperField } from "@poirazis/supercomponents-shared";

  const { styleable, memo } = getContext("sdk");
  const component = getContext("component");

  const formContext = getContext("form");
  const formStepContext = getContext("form-step");
  const groupLabelPosition = getContext("field-group");
  const labelWidth = getContext("field-group-label-width");
  const groupColumns = getContext("field-group-columns");
  const groupDisabled = getContext("field-group-disabled");
  const formApi = formContext?.formApi;

  export let field = "Icon Field";
  export let label;
  export let span = 6;
  export let placeholder;
  export let defaultValue;
  export let template;
  export let disabled;
  export let readonly;
  export let validation;
  export let labelPosition = "fieldGroup";

  export let onChange;
  export let debounced;
  export let debounceDelay;

  export let showCategories;

  export let helpText;

  let formField;
  let formStep;
  let fieldState;
  let fieldApi;
  let fieldSchema;
  let value;

  $: formStep = formStepContext ? $formStepContext || 1 : 1;
  $: labelPos =
    groupLabelPosition && labelPosition == "fieldGroup"
      ? groupLabelPosition
      : labelPosition;

  $: formField = formApi?.registerField(
    field,
    "string",
    defaultValue,
    disabled,
    readonly,
    validation,
    formStep
  );

  $: unsubscribe = formField?.subscribe((value) => {
    fieldState = value?.fieldState;
    fieldApi = value?.fieldApi;
    fieldSchema = value?.fieldSchema;
  });

  $: value = fieldState?.value ? fieldState.value : defaultValue;
  $: error = fieldState?.error;

  $: cellOptions = {
    placeholder,
    defaultValue,
    disabled: disabled || groupDisabled || fieldState?.disabled,
    template,
    readonly: readonly || fieldState?.readonly,
    padding: "0.5rem",
    readonly: readonly || disabled,
    debounce: debounced ? debounceDelay : false,
    error: fieldState?.error,
    role: "formInput",
    showCategories,
  };

  $: $component.styles = {
    ...$component.styles,
    normal: {
      ...$component.styles.normal,
      "grid-column": span < 7 ? "span " + span : "span " + groupColumns * 6,
      flex: span > 6 ? "auto" : "none",
    },
  };

  const handleChange = (newValue) => {
    onChange?.({ value: newValue });
    fieldApi?.setValue(newValue);
  };

  onDestroy(() => {
    fieldApi?.deregister();
    unsubscribe?.();
  });
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-noninteractive-tabindex -->
<div use:styleable={$component.styles}>
  <SuperField {labelPos} {labelWidth} {field} {label} {error} {helpText}>
    <CellIcon
      {cellOptions}
      {value}
      {fieldSchema}
      on:change={(e) => handleChange(e.detail)}
    />
  </SuperField>
</div>
