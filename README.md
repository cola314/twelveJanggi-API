# twelveJangi-API (십이장기 API)


##### 십이장기 게임을 쉽게 관리 할 수 있는 api


# Game class
전반적인 게임 조작들을 하는 클래스

## Game.init_game()
게임 내부 설정들을 초기화

## Game.set_turn(player)
말을 옮길 차례를 설정

~~~javascript
//player는 1과 2만 가능
Game.set_first(1);
Game.set_fisrt(2);
~~~

## Game.get_board
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
  
# MAL class
게임 말의 종류, 진행 가능 방향, 상태를 정의

## MAL.type
* type : <string>
  + "Wang" 왕(王)
  + "Sang" 상(相)
  + "Jang" 장(將)
  + "Ja"   자(子)
  + "Hu"   후(侯)
  
## MAL.player
* type : <Number>
  + 1   플레이어 1
  + 2   플레이어 2
  
## MAL.highlighted
* type : <boolean>
플레이어가 말을 선택하면 이동 가능한 칸이 하이라이트 되는데 이 여부를 반환
