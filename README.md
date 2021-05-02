# ゲームのルール

Multiple players fight against one another. Played by more than 2 players.   
The main cards are `trust`, `doubt`, and `attack`.   

Each round of the game consists of two steps.

In the first steps, players choose one of the cards dealt and receive rewards.  
- When one chooses to `trust`, he gets a reward if no other players use `attack`. If any of the other players use `attack`, then he loses a score worth -$a. 
- When one chooses to `doubt`, he loses score if no other players use `attack`. The score he loses is dependent on the proportion of the other players that use `trust`.
If any of the other players use `attack`, he does not lose score.
- When one chooses to  `attack`, he gets a reward proportional to the number of the player that chose `trust`. 

In the next step, players discuss which person used `attack` and vote.  
If the most-voted player did use `attack`, then he loses some score.  
If not, then the player that voted the most-voted players lose some score.

# 実装について

# 目標
- ユーザーが1vs1で通信できるようにする
    - 通信して選んだカードをサーバーに送りつけて何かしらの得点を受け取る

# サーバー
- POST create_room () => {
    room_id,
    socket?
}
- POST enter_room ( room_id ) => {
    socket
}
- POST choose_card ( room_id, card, player_id )
    - Websocket で 結果を流す

# クライアント
