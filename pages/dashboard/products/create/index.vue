<script setup lang="ts">
definePageMeta({
  layout: "custom",
});
import { useForm } from "vee-validate";
import { toTypedSchema } from "@vee-validate/zod";
import * as z from "zod";

import { Button } from "@/components/ui/button";
import {
  FormControl,
  FormDescription,
  FormField,
  FormItem,
  FormLabel,
  FormMessage,
} from "@/components/ui/form";
import { Input } from "@/components/ui/input";

const formSchema = toTypedSchema(
  z.object({
    username: z.string().min(2).max(50),
  })
);

const form = useForm({
  validationSchema: formSchema,
});

const onSubmit = form.handleSubmit((values) => {
  console.log("Form submitted!", values);
});
</script>

<template>
  <div class="w-1/2 mx-auto mt-10">
    <h1 class="text-2xl font-bold mb-4">Create Product</h1>
    <form @submit="onSubmit">
      <FormField v-slot="{ componentField }" name="name">
        <FormItem>
          <FormLabel>Name</FormLabel>
          <FormControl>
            <Input type="text" placeholder="name" v-bind="componentField" />
          </FormControl>
          <FormDescription> This is your public display name. </FormDescription>
          <FormMessage />
        </FormItem>
        <FormItem>
          <FormLabel>Price</FormLabel>
          <FormControl>
            <Input type="text" placeholder="price" v-bind="componentField" />
          </FormControl>
          <FormDescription> This is your public display name. </FormDescription>
          <FormMessage />
        </FormItem>
        <FormItem>
          <FormLabel>Description</FormLabel>
          <FormControl>
            <Input type="text" placeholder="name" v-bind="componentField" />
          </FormControl>
          <FormDescription> This is your public display name. </FormDescription>
          <FormMessage />
        </FormItem>
        <FormItem>
          <FormLabel>Image</FormLabel>
          <FormControl>
            <Input type="file" placeholder="name" v-bind="componentField" />
          </FormControl>
          <FormDescription> This is your public display name. </FormDescription>
          <FormMessage />
        </FormItem>
      </FormField>
      <Button type="submit"> Submit </Button>
    </form>
  </div>
</template>
