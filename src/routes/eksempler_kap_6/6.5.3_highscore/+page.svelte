<script>
// @ts-nocheck

// Her henter vi ut de variablene som er lagret i stores
import { highscores } from '../stores'

/*
  På alle variablene kan vi bruke: set, update, og $
  variabel.set() - for å endre verdien NB: Husk at variablen blir overskreven helt!
  variabel.update(data=>{data.endret = "nyVerdi"; return data})
  $variabel - for å hente ut verdien OG lytte på mulige endringer.
*/

let navn = ""
let score = 0

function sorted(highscores){
  highscores.sort((a,b)=>b[1]-a[1])
  return highscores
}

function sendinn(){
  console.log("JADA")
  highscores.update(data=>{data.push([navn, score]); return data})
  navn = ""
  score = 0
  highscores = highscores
}

</script>
<h1>Highscore Car Game</h1>
<main>
<ol>
{#each sorted($highscores) as score}
  <li>{score[0]} : {score[1]}</li>
{/each}
</ol>
<div>
  <label>Navn: <input type="text" bind:value={navn}></label>
  <label>Score: <input type="number" bind:value={score}></label>
  <button on:click={sendinn}>Registrer</button>
</div>
</main>
<style>
  main{
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
</style>