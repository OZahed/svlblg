<script lang="ts">
	import type { Post } from "./types";

    export let post: Post;
    export let index: number;
    let slug = post.title.replaceAll(' ', '-').toLowerCase();
</script>

<div class="mb-4 flex flex-col md:flex-row {index % 2 === 0 ? 'md:flex-row-reverse' : ''} items-center space-x-4">
    <div class="w-full md:w-1/3 h-48 md:h-auto overflow-hidden relative">
        <img src={post.image} alt={post.title} class="pb-2 md:pb-0 absolute top-0 left-0 object-cover w-full h-full rounded-md md:relative md:static" />
    </div>
	<hr class="my-2 mx-auto border-solid border-gray-400 w-1/2 md:hidden"/>
    <div class="w-full md:w-2/3">
        <h3 class="text-lg font-semibold">{index + 1} - {post.title}</h3>
        <p class="text-sm text-gray-500">{post.date} by {post.author}</p>
        <p class="text-gray-700">
            {post.text}
        </p>
        <div>
            <a href={`/blog/${slug}`}><strong>Read more →</strong></a>
        </div>
    </div>
</div>

