<script setup lang="ts">
// meta title
useHead({
  title: 'Edit a Post - robbocode.com',
});

// init config
const config = useRuntimeConfig();

// init router
const router = useRouter();

// init route
const route = useRoute();

// fetch daa for get detail data post
const { data:post } : any = await useFetch(`${config.public.apiBase}/api/posts/${route.params.id}`);

// define state
const image = ref('');
const title = ref(post.value.data.title);
const content = ref(post.value.data.content);
const errors : any = ref({});

// method for handle file changes
const handleFileChange = ( e: any ) => {

  // asign file to state
  image.value = e.target.files[0]
}


</script>

<template>
  <div>
    Page: foo
  </div>
</template>

<style scoped></style>
