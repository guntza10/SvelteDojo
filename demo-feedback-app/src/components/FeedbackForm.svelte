<script>
  import { v4 as uuidv4 } from "uuid";

  import { createEventDispatcher } from "svelte";

  import { FeedbackStore } from "../store";

  import Button from "./Button.svelte";
  import Card from "./Card.svelte";
  import RatingSelect from "./RatingSelect.svelte";

  const dispatch = createEventDispatcher();

  let text = "";
  let rating = 10;
  let btnDisabled = true;
  let minLength = 10;
  let message;

  const handleSelect = (e) => {
    rating = parseInt(e.detail);
  };

  const handleInput = () => {
    if (text.trim().length <= minLength) {
      message = `Text must be at least ${minLength} characters`;
      btnDisabled = true;
    } else {
      message = null;
      btnDisabled = false;
    }
  };

  // with dispatch custom event
  const handleSubmit = () => {
    if (text.trim().length > minLength) {
      const newFeedback = {
        id: uuidv4(),
        text,
        rating,
      };

      dispatch("add-feedback", newFeedback);

      text = "";
      rating = 10;
    }
  };

  // with access directly store
  const handleSubmit2 = () => {
    if (text.trim().length > minLength) {
      const newFeedback = {
        id: uuidv4(),
        text,
        rating,
      };

      FeedbackStore.update((currentFeedback) => {
        return [newFeedback, ...currentFeedback];
      });

      text = "";
      rating = 10;
    }
  };
</script>

<Card>
  <header>
    <h2>How would you rate your service with us?</h2>
  </header>
  <!-- with dispatch custom event -->
  <!-- <form on:submit|preventDefault={handleSubmit}> -->

  <!-- with access directly store -->
  <form on:submit|preventDefault={handleSubmit2}>
    <RatingSelect on:rating-select={handleSelect} {rating} />
    <div class="input-group">
      <input
        type="text"
        placeholder="Tell us something that keeps you coming back"
        bind:value={text}
        on:input={handleInput}
      />
      <Button type="submit" disabled={btnDisabled}>Send</Button>
    </div>
    {#if message}
      <div class="message">{message}</div>
    {/if}
  </form>
</Card>

<style>
  header {
    max-width: 400px;
    margin: auto;
  }
  header h2 {
    font-size: 22px;
    font-weight: 600;
    text-align: center;
  }
  .input-group {
    display: flex;
    flex-direction: row;
    border: 1px solid #ccc;
    padding: 8px 10px;
    border-radius: 8px;
    margin-top: 15px;
  }
  input {
    flex-grow: 2;
    border: none;
    font-size: 16px;
  }
  input:focus {
    outline: none;
  }
  .message {
    padding-top: 10px;
    text-align: center;
    color: rebeccapurple;
  }
</style>
