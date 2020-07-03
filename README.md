# twelveJangi-API (십이장기 API)


##### 십이장기 게임을 쉽게 관리 할 수 있는 api
<hr>

# Game class
## Game.init_game()
게임 내부 설정들을 초기화

## Game.set_turn(player)
말을 옮길 차례를 설정

~~~javascript
//player는 1과 2만 가능
Game.set_first(1);
Game.set_fisrt(2);
~~~

## Game.getBoard
* returns MAL[3][4]
현재 보드 정보를 반환한다
보드 정보는 MAL 객체 배열로 반환된다

~~~javascript
board = Game.getBoard();
console.log(board[1][1].type);
~~~

## Game.get_having(player)
* returns <array<MAL>> 
player가 딴 말을 저장한 배열을 반환

~~~javascript
p1_having = Game.get_having(1);
p2_having = Game.get_having(2);
~~~


## Game.button_click(player, button_y, button_x)
* returns <success> 무효한 입력에는 0, 말이 선택되면 1, 말이 옮겨지면 2
  
~~~javascript
// 플레이어 1이 2, 2 버튼을 눌렸을 때 
if(Game.button_click(player, 2, 2) == 2) {
  Game.set_turn(2);
}
~~~

## Game.state()
* returns <state> 플레이어 1이 승리시 1, 플레이어 2가 승리시 2, 나머지 0
  
  ~~~javascript
  winner = Game.state();
  if(winner != 0) {
    console.log(i + " is Win");
  }
  ~~~
  
  
