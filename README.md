# task-1
[7:46 PM, 4/1/2024] Varshini M: <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tic Tac Toe</title>
<link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
<div class="container">
  <h1>Tic Tac Toe</h1>
  <div id="board" class="board">
    <div class="cell" onclick="cellClicked(0)"></div>
    <div class="cell" onclick="cellClicked(1)"></div>
    <div class="cell" onclick="cellClicked(2)"></div>
    <div class="cell" onclick="cellClicked(3)"></div>
    <div class="cell" onclick="cellClicked(4)"></div>
    <div class="cell" onclick="cellClicked(5)"></div>
    <div class="cell" onclick="cellClicked(6)"></div>
    <div class="cell" onclick="cellClicked(7)"></div>
    <div class="cell" …
[7:47 PM, 4/1/2024] Varshini M: let currentPlayer = 'X';
let board = ['', '', '', '', '', '', '', '', ''];
const winningCombos = [
  [0, 1, 2],
  [3, 4, 5],
  [6, 7, 8],
  [0, 3, 6],
  [1, 4, 7],
  [2, 5, 8],
  [0, 4, 8],
  [2, 4, 6]
];

const cells = document.querySelectorAll('.cell');
const message = document.getElementById('message');

function cellClicked(index) {
  if (board[index] === '' && !checkWinner()) {
    board[index] = currentPlayer;
    cells[index].textContent = currentPlayer;
    if (checkWinner()) {
      message.textContent = ${currentPlayer} wins!;
    } else if (board.every(cell => cell !== '')) {
      message.textContent = 'It\'s a draw!';
    } else {
      currentPlayer = currentPlayer === 'X' ? 'O' : 'X';
      message.textContent = Player ${currentPlayer}'s turn;…
[7:48 PM, 4/1/2024] Varshini M: .container {
  text-align: center;
}

.board {
  display: grid;
  grid-template-columns: repeat(3, 100px);
  grid-template-rows: repeat(3, 100px);
  gap: 2px;
  margin-bottom: 20px;
}

.cell {
  background-color: #eee;
  border: 1px solid #aaa;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 40px;
  cursor: pointer;
}

button {
  font-size: 16px;
  padding: 10px 20px;
  background-color: #007bff;
  color: #fff;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}
