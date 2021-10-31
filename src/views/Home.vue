<template>
  <div class="home">
    <FormProvider :form="form">
      <SchemaField
        :schema="{
          type: 'object',
          properties: {
            input: {
              type: 'string',
              'x-component': 'Input',
              'x-component-props': {
                placeholder: 'test',
              },
              'x-decorator': 'FormItem',
              'x-decorator-props': {
                label: 'test',
              },
            },
          },
        }"
      >
      </SchemaField>
    </FormProvider>
  </div>
</template>

<script>
// @ is an alias to /src
import { Input, Form } from "ant-design-vue";
import { createForm } from "@formily/core";
import { FormProvider, createSchemaField } from "@formily/vue";

const { SchemaField } = createSchemaField({
  components: {
    Input,
    FormItem: Form.Item,
  },
});

export default {
  components: { FormProvider, SchemaField },
  data() {
    return {
      form: createForm(),
    };
  },
};
</script>

<style scoped>
.home {
  width: 800px;
  margin: 0 auto;
}
</style>
