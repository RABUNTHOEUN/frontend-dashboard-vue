<script setup lang="ts">
import { ref, onMounted } from 'vue'
import axios from 'axios'

import {
  Table,
  TableBody,
  TableCaption,
  TableCell,
  TableHead,
  TableHeader,
  TableRow,
} from "@/components/ui/table"

import { Button } from "@/components/ui/button"

definePageMeta({
  layout: "custom",
})

// Category type
interface Category {
  id: number
  name: string
  description: string
  products: any[]
}

// State
const categories = ref<Category[]>([])

// Fetch data from API using Axios
const fetchCategories = async () => {
  try {
    const response = await axios.get<Category[]>('http://localhost:5044/api/Categories')
    categories.value = response.data
  } catch (error) {
    console.error('Error fetching categories:', error)
  }
}

// Run on mounted
onMounted(fetchCategories)
</script>

<template>
  <div class="flex flex-1 flex-col gap-4 pt-0">
    <div class="flex items-center justify-between">
      <h1 class="text-xl pl-2">Categories</h1>
      <Button>New</Button>
    </div>
    <Table>
      <TableCaption>A list of your recent categories.</TableCaption>
      <TableHeader>
        <TableRow>
          <TableHead class="w-[100px]">ID</TableHead>
          <TableHead>Name</TableHead>
          <TableHead>Description</TableHead>
          <TableHead>Products Count</TableHead>
          <TableHead class="text-right">Action</TableHead>
        </TableRow>
      </TableHeader>
      <TableBody>
        <TableRow v-for="category in categories" :key="category.id">
          <TableCell class="font-medium">{{ category.id }}</TableCell>
          <TableCell>{{ category.name }}</TableCell>
          <TableCell>{{ category.description }}</TableCell>
          <TableCell>{{ category.products.length }}</TableCell>
          <TableCell class="text-right space-x-2">
            <Button>View</Button>
            <Button variant="outline">Edit</Button>
            <Button variant="destructive">Delete</Button>
          </TableCell>
        </TableRow>
      </TableBody>
    </Table>
  </div>
</template>
