## Rotas API REST
  OBS: Para todas as rotas, menos o create de user, e necessário ter setado anteriormente cookie de sessão através da rota do create user
  
  #### namespace administrative
    rest_resources for questionaires
    rest_resources for questions
    rest_resources for alternative
  ##### namespace /
    rest_resources for rooms
    rest_resources for users( criar um user e seta o "cookie de sessão")

### Rotas WebSocket
  Rota base de conexão: "ws://localhost:3000/cable"

  #### subscribe
  Enviar mensagem via websocket no formato:

    command: "subscribe",
    identifier: { 
      channel: "RoomsChannel", 
      room_id: "efa85f58-4fdb-4d30-9836-f5a5efe5c4f9"
    }
  
  #### init_game
  Enviar mensagem via websocket no formato:

    command: "message",
    identifier: {
      channel: "RoomsChannel",
      room_id: "efa85f58-4fdb-4d30-9836-f5a5efe5c4f9"
    },
    data: {
      action: 'init_game'
    }

  #### show_current_scoreboard
  Enviar mensagem via websocket no formato:

    command: "message",
    identifier: {
      channel: "RoomsChannel",
      room_id: "efa85f58-4fdb-4d30-9836-f5a5efe5c4f9"
    },
    data: {
      action: 'show_current_scoreboard'
    }

  #### register_answer
  Enviar mensagem via websocket no formato:

    command: "message",
    identifier: {
      channel: "RoomsChannel",
      room_id: "efa85f58-4fdb-4d30-9836-f5a5efe5c4f9"
    },
    data: {
      action: 'register_answer',
      alternative_position: 'a'
    }

  #### unsubscribed
  Apenas fechar a conexão