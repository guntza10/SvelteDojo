<script>
  import Card from "./Card.svelte";
  import { createEventDispatcher } from "svelte";
  export let item;

  import { FeedbackStore } from "../store";

  const dispatch = createEventDispatcher();

  // with dispatch custom event
  const handleDelete = (itemId) => {
    dispatch("delete-feedback", itemId);
  };

  // with access directly store
  const handleDelete2 = (itemId) => {
    FeedbackStore.update((currentFeedback) => {
      return currentFeedback.filter((it) => it.id !== itemId);
    });
  };
</script>

<Card>
  <div class="num-display">
    {item.rating}
  </div>
  <!-- with dispatch custom event -->
  <!-- <button class="close" on:click={() => handleDelete(item.id)}>X</button> -->

  <!-- with access directly store -->
  <button class="close" on:click={() => handleDelete2(item.id)}>X</button>
  <p class="text-display">{item.text}</p>
</Card>

<style>
  .num-display {
    position: absolute;
    top: -10px;
    left: -10px;
    width: 50px;
    height: 50px;
    background: #ff6a95;
    color: #fff;
    border: 1px #eee solid;
    border-radius: 50%;
    padding: 10px;
    text-align: center;
    font-size: 19px;
  }
  .close {
    position: absolute;
    top: 10px;
    right: 20px;
    cursor: pointer;
    background: none;
    border: none;
  }
</style>
