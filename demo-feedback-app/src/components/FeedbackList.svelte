<script>
  // import { onMount, onDestroy } from "svelte";
  import { fade, scale, slide } from "svelte/transition";
  import FeedbackItem from "./FeedbackItem.svelte";

  // with dispatch custom event
  // export let feedbacks;

  // ไม่ได้ get จาก props แล้วแต่เปลี่ยนไป get จาก store แทน (access directly store)
  import { FeedbackStore } from "../store";

  //   let feedbacks;
  //  const unsubscribe = FeedbackStore.subscribe((data) => (feedbacks = data));

  //   onMount(() => {
  //     console.log("mounted");
  //   });

  //   onDestroy(() => {
  //     console.log("destroyed");
  //     unsubscribe();
  //   });
</script>

<!-- with dispatch custom event -->
<!-- {#each feedbacks as feedback (feedback.id)} -->

<!-- ถ้าใช้ท่านี้จะเป็นแบบย่อที่ไม่ต้องจัดการท่าข้างบน แล้วมันยัง auto unsubscribe ให้ด้วย เป็นการ access directly store -->
{#each $FeedbackStore as feedback (feedback.id)}
  <!-- ส่ง custom event forward up ขึ้นไปเรื่อยๆ ถ้าต้องการ catch ให้ทำการ define function ถ้าไม่ define function มันจะถูก forward ส่งขึ้นไปให้ component ชั้นบนต่อไป -->
  <!-- <div transition:fade>  -->
  <!-- transition จะแตกต่างกับ in,out ตรงที่จะทำทั้งการ in,out -->
  <div in:scale out:fade={{ duration: 500 }}>
    <!-- with dispatch custom event -->
    <!-- <FeedbackItem item={feedback} on:delete-feedback /> -->

    <!-- with access directly store -->
    <FeedbackItem item={feedback} />
  </div>
{/each}
