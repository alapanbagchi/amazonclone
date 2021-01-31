<script>
  export let footer;
  let contents = footer.content;
  let open = "open";
  $: console.log(open)
  $: console.log(document.body.clientWidth)
  if(document.body.clientWidth<1200)
  {  
    open = ""
  }
</script>

<div class="footer_wrapper">
  <div class="sub_footer">
    {#each footer as item}
      <details id="details" {open} >
        <summary>{item.name}</summary>
        <div  class="content">
          {#each item.content as content}
            <p>{content}</p>
          {/each}
        </div>
      </details>
    {/each}
  </div>
  <div class="main_footer">
    <div class="info">
      <img src="./assets/amazonlogo.svg" alt="" />
      <p>© 1996-2021</p>
      <p>Conditions of Use and Sale</p>
      <p>Privacy Notice</p>
    </div>
  </div>
</div>

<style>
  details {
    padding-bottom: 3em;
    cursor: pointer;
    outline: none;
    border: none;
    display: flex;
    justify-content: center;
  }
  details summary::-webkit-details-marker {
    display: none;
  }
  summary {
    font-weight: 700;
    font-size: 1em;
    color: var(--text-primary);
    outline: none;
  }
  .footer_wrapper {
    width: 100%;
    height: 90vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .sub_footer {
    width: 80%;
    height: 90%;
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    border-bottom: 1px solid #d6d6d6;
    margin-top: 20vh;
  }

  .content {
    margin-top: 1em;
    font-weight: 400;
    color: var(--text-secondary);
  }
  .content p {
    margin-top: 1.5em;
    cursor: pointer;
  }
  .main_footer {
    width: 80%;
    height: 20%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .info {
    display: flex;
    gap: 50px;
    font-weight: 400;
    color: var(--text-secondary);
  }
  .info p {
    cursor: pointer;
  }
  .info img {
    width: 100px;
  }
  @media only screen and (max-width: 1200px) {
    .footer_wrapper {
      height: fit-content;
    }
    details summary::-webkit-details-marker {
      display: flex;
      color: var(--amazon-yellow);
    }
    .content {
      display: flex;
      justify-content: center;
      align-self: center;
      flex-direction: column;
    }
    .info p {
      display: none;
    }
    .sub_footer {
      display: flex;
      flex-direction: column;
      height: fit-content;
      padding-top: 10vh;
      padding-bottom: 5vh;
      margin: 0;
    }
    details {
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .main_footer
    {
      height: 5em;
    }
    summary
    {
      display: flex;
      align-items: center;
    }
  }
</style>
