---
layout: page
title: offline centers
background: grey
---

<div class="container">
  <div class="switches-container">
    <input type="radio" id="switchGallery" name="switchPlan" value="Gallery" checked="checked" />
    <input type="radio" id="switchTeam" name="switchPlan" value="Team" />
    <input type="radio" id="switchThird" name="switchPlan" value="ThirdOption" />
    <label for="switchGallery">Gallery</label>
    <label for="switchTeam">Team</label>
    <label for="switchThird">ThirdOption</label>
    <div class="switch-wrapper">
      <div class="switch">
        <div>Gallery</div>
        <div>Team</div>
        <div>ThirdOption</div>
      </div>
    </div>
  </div>
</div>

<style>
    * {
    box-sizing: border-box;
}
:root {
    --switches-bg-color: #AFCB1E;
    --switches-label-color: white ;
    --switch-bg-color: white;
    --switch-text-color: #AFCB1E ;
}
body {
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
/* container for all of the switch elements 
    - adjust "width" to fit the content accordingly 
*/
.switches-container {
    width: 36rem;
    position: relative;
    display: flex;
    padding: 0;
    position: relative;
    background: var(--switches-bg-color);
    line-height: 3rem;
    border-radius: 3rem;
    margin-left: auto;
    margin-right: auto;
}
/* input (radio) for toggling. hidden - use labels for clicking on */
.switches-container input {
    visibility: hidden;
    position: absolute;
    top: 0;
}
/* labels for the input (radio) boxes - something to click on */
.switches-container label {
    width: 33.33%;
    padding: 0;
    margin: 0;
    text-align: center;
    cursor: pointer;
    color: var(--switches-label-color);
}
/* switch highlighters wrapper (sliding left / right) 
    - need wrapper to enable the even margins around the highlight box
*/
.switch-wrapper {
    position: absolute;
    top: 0;
    bottom: 0;
    width: 33.33%;
    padding: 0.15rem;
    z-index: 3;
    transition: transform .5s cubic-bezier(.77, 0, .175, 1);
    /* transition: transform 1s; */
}
/* switch box highlighter */
.switch {
    border-radius: 3rem;
    background: var(--switch-bg-color);
    height: 100%;
}
/* switch box labels
    - default setup
    - toggle afterwards based on radio:checked status 
*/
.switch div {
    width: 100%;
    text-align: center;
    opacity: 0;
    display: block;
    color: var(--switch-text-color) ;
    transition: opacity .2s cubic-bezier(.77, 0, .175, 1) .125s;
    will-change: opacity;
    position: absolute;
    top: 0;
    left: 0;
}
/* slide the switch box from right to left */
.switches-container input:nth-of-type(1):checked~.switch-wrapper {
    transform: translateX(0%);
}
/* slide the switch box from left to right */
.switches-container input:nth-of-type(2):checked~.switch-wrapper {
    transform: translateX(100%);
}
/* toggle the switch box labels - first checkbox:checked - show first switch div */
.switches-container input:nth-of-type(1):checked~.switch-wrapper .switch div:nth-of-type(1) {
    opacity: 1;
}
/* toggle the switch box labels - second checkbox:checked - show second switch div */
.switches-container input:nth-of-type(2):checked~.switch-wrapper .switch div:nth-of-type(2) {
    opacity: 1;
}
    #switchThird {
      /* Adjust styles as needed */
      background-color: #3498db;
      color: white;
    }

    #switchThird:checked~.switch-wrapper {
      transform: translateX(200%);
    }

    #switchThird:checked~.switch-wrapper .switch div:nth-of-type(3) {
      opacity: 1;
    }
  </style>