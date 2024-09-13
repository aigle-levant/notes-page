---
layout: post
title: JS - Projects
categories: [JS]
---

Here are some projects I did in JS, along with my workaround...

* Table of content
{:toc}

## Projects

### Rock-paper-scissors

```js
function getComputerChoice()
{
    let randNum = Math.floor(Math.random() * 3)
    if (randNum===0)
    {
        return "rock";
    }
    else if (randNum===1)
    {
        return "paper";
    }
    else if (randNum===2)
    {
        return "scissors";
    }
    else
    {
        return "Value not found";
    }
}

function getHumanChoice()
{
    const prompt = require("prompt-sync")({sigint:true});
    console.log("rock / paper / scissors");
    let humanOption = prompt("Enter your choice: ");
    humanOption = humanOption.toLowerCase();
    if (humanOption==="")
    {
        return "Invalid input";
    }
    return humanOption;
}

function playRound(humanChoice, computerChoice)
{
    let drawMessage = "it's a draw! ";
    let winMessage = ("it's a win! " + humanChoice + " beats " + computerChoice);
    let loseMessage = ("it's a loss! " + computerChoice + " beats " + humanChoice);

    if (humanChoice==="rock" && computerChoice==="rock"
        || humanChoice==="paper" && computerChoice==="paper"
        || humanChoice==="scissors" && computerChoice==="scissors")
    {
        return drawMessage;
    }
    else if (humanChoice==="rock" && computerChoice==="paper" ||
        humanChoice==="scissors" && computerChoice==="rock" ||
        humanChoice==="paper" && computerChoice==="scissors") 
    {
        computerScore++;
        return loseMessage;
    }
    else if (humanChoice==="rock" && computerChoice==="scissors" ||
        humanChoice==="scissors" && computerChoice==="paper" ||
        humanChoice==="paper" && computerChoice==="rock")
    {
        humanScore++;
        return winMessage;
    }
    else
    {
        return "Error";
    }
}

function playGame()
{
    for (let i=0;i<=5;i++)
    {
        const humanSelection = getHumanChoice();
        const computerSelection = getComputerChoice();
        console.log(playRound(humanSelection, computerSelection));
    }
}
let humanScore = 0;
let computerScore = 0;

console.log(playGame());
console.log("Final score: ");
console.log("Human: " + humanScore + "\nComputer: " + computerScore);

```

### Stopwatch


