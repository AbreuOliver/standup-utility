<script>
  let assignee = "5e5e93754befbd0c96cade95";
  let URL = `https://extron.atlassian.net/rest/api/2/search?jql=assignee=${assignee} AND project=GVIL AND (status="In Progress" OR status="UX Verify" OR status="Code Review" OR status="Under Verification" OR status="PO Verify")`;
  let username = `oabreu@extron.com`;
  let password = `kPcXZKUwrw62BPPCMz9v18E4`;

  function handleClick() {
    fetch(`${URL}`, {
      mode: "cors",
      // redirect: "follow",
      headers: {
        Authorization:
          "Basic b2FicmV1QGV4dHJvbi5jb206a1BjWFpLVXdydzYyQlBQQ016OXYxOEU0",
        Cookie:
          "atlassian.xsrf.token=BXI3-ZNEU-UCR4-LTUK_a9b227cf97ab27686187e4ac4f15c6fc292d406a_lin",
        // "Postman-Token": "52d84690-079f-4ed1-b849-4455d7c65924",
        Host: "extron.atlassian.net",
        "Access-Control-Allow-Origin": "http://localhost:5173",
      },
      referrerPolicy: "no-referrer-when-downgrade",
    })
      // .then((response) => response.json())
      .then((data) => {
        console.log(data);
        // apiData.set(data);
      })
      .catch((error) => {
        console.log(error);
        return [];
      });
  }
</script>

<main class="container">
  <div class="left">
    <h1>TMI Standup Utility</h1>
    <button on:click|once={handleClick}>Oliver A</button>
  </div>
  <div class="right">
    <p class="read-the-docs">
      Click on the Vite and Svelte logos to learn more
    </p>
  </div>
</main>

<style>
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100vw;
    height: 100vh;
    overflow: none;
    margin: 0 auto;
  }
  .left {
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    -moz-box-sizing: border-box;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
    padding: 150px 0 150px 150px;
    height: 100vh;
    /* width: 66%; */
    background-color: #2d4c8a;
    color: white;
  }
  button {
    min-width: 150px;
    max-width: 250px;
    height: 50px;
  }

  button:focus {
    border: none;
  }

  .right {
    display: flex;
    flex-direction: column;
    flex-grow: 3;
    height: 100vh;
    /* width: 33%; */
  }
</style>
