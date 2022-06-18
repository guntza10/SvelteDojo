<script>
  import FeedbackList from "./components/FeedbackList.svelte";
  import FeedbackStats from "./components/FeedbackStats.svelte";
  import FeedbackForm from "./components/FeedbackForm.svelte";

  // with dispatch custom event
  // let feedbacks = [
  //   {
  //     id: 1,
  //     rating: 10,
  //     text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.",
  //   },
  //   {
  //     id: 2,
  //     rating: 9,
  //     text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.",
  //   },
  //   {
  //     id: 3,
  //     rating: 8,
  //     text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.",
  //   },
  // ];

  // with dispatch custom event
  // $: count = feedbacks.length;
  // $: average =
  //   feedbacks.reduce((prev, current) => prev + current.rating, 0) / count;

  // with dispatch custom event
  // const deleteFeedback = (e) => {
  //   console.log("e.detail", e.detail); // e.detail => value ที่ catch ได้จากการ dispatch
  //   feedbacks = feedbacks.filter((it) => it.id !== e.detail);
  // };

  // with dispatch custom event
  // const addFeedback = (e) => {
  //   feedbacks = [e.detail, ...feedbacks];
  // };
</script>

<main class="container">
  <!-- with dispatch custom event -->
  <!-- <FeedbackForm on:add-feedback={addFeedback} /> -->
  <!-- <FeedbackStats {count} {average} /> -->
  <!-- <FeedbackList {feedbacks} on:delete-feedback={deleteFeedback} /> -->

  <!-- with access directly store -->
  <FeedbackForm />
  <FeedbackStats />
  <FeedbackList />
</main>

<style>
</style>
