<script lang="ts">
export const description = "A sidebar that collapses to icons.";
export const iframeHeight = "800px";
export const containerClass = "w-full h-full";
definePageMeta({
  layout: "custom",
});

import {
  Table,
  TableBody,
  TableCaption,
  TableCell,
  TableHead,
  TableHeader,
  TableRow,
} from "@/components/ui/table";
</script>

<template>
  <div class="flex flex-1 flex-col gap-4 pt-0">
    <div class="flex items-center justify-between">
      <h1 class="text-xl pl-2">Catetories</h1>
      <Button>New</Button>
    </div>
    <Table>
      <TableCaption>A list of your recent categories.</TableCaption>
      <TableHeader>
        <TableRow>
          <TableHead class="w-[100px]"> ID </TableHead>
          <TableHead>Image</TableHead>
          <TableHead>Name</TableHead>
          <TableHead>Description</TableHead>
          <TableHead>Price</TableHead>
          <TableHead class="text-right"> Action </TableHead>
        </TableRow>
      </TableHeader>
      <TableBody>
        <TableRow>
          <TableCell class="font-medium"> INV001 </TableCell>
          <TableCell>1.jpg</TableCell>
          <TableCell>Apple</TableCell>
          <TableCell>Black Apple</TableCell>
          <TableCell>$250.00 </TableCell>
          <TableCell class="text-right space-x-2">
            <Button> View </Button>
            <Button variant="outline"> Edit </Button>
            <Button variant="destructive"> Delete </Button>
          </TableCell>
        </TableRow>
      </TableBody>
    </Table>
  </div>
</template>
