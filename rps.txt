// lets do this! lets make ROCK PAPER SCISSORS!


var player;
var computer = 0;
var rock = 1;
var paper = 2;
var scissors = 3;
var playerWins = 0;
var ties = 0;
var playerLoses = 0;
var rounds = 0;


// randomly generates the computers choice
var computerSelection = function() {
  computer = Math.floor((Math.random() * 3) + 1);
  if (computer == 1) 
  {
    computer = rock;
  }
  else if (computer == 2) 
  {
    computer = paper;
  }
  else
  {
    computer = scissors;
  }
  return computer;
}


var runGame = function(computer, player) {
  if (computer == rock && player == rock)
  {
    ties++;
    rounds++;
    alert("Its a Tie");
  }
  else if (computer == rock && player == paper)
  {
    playerWins++;
    rounds++;
    alert("You Win");
  }
  else if (computer == rock && player == scissors)
  {
    playerLoses ++;
    rounds++;
    alert("You Lose");
  }
  else if (computer == paper && player == rock)
  {
    playerLoses ++;
    rounds++;
    alert("You Lose");
  }
  else if (computer == paper && player == paper)
  {
    ties++
    rounds++;
    alert("Its a Tie");
  }
  else if (computer == paper && player == scissors)
  {
    playerWins++;
    rounds++;
    alert("You Win");
  }
  else if (computer == scissors && player == rock)
  {
    playerWins++;
    rounds++;
    alert("You Win");
  }
  else if (computer == scissors && player == paper)
  {
    playerLoses++; 
    rounds++;
    alert("You Lose");
  }
  else if (computer == scissors && player == scissors)
  {
    ties++
    rounds++;
    alert("Its a Tie");
  }
}
var playerSelection = function() {

  // getting player input
  player = prompt("Choose your Weapon.. Rock.. Paper.. Scissors");

    switch (player) {
      case "rock":
      case "Rock":
      case "ROCK":
        player = rock;
        break;
      case "paper":
      case "Paper":
      case "PAPER":
        player = paper;
        break;
      case "scissors":
      case "Scissors":
      case "SCISSORS":
        player = scissors;
        break;        
      default:
        alert("make a selection");
    }
    return player;
  
  
}

var scoreBoard = function() {
  alert("Rounds played: " + rounds + " Wins: " + playerWins + " Losses: " + playerLoses);
}




playerSelection();
computerSelection();
runGame(computer, player);
scoreBoard();



