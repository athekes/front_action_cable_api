## Rotas API REST
  OBS: Para todas as rotas, menos o create de user, e necessário ter setado anteriormente cookie de sessão atravez da rota do create user
  
  #### namespace administrative
    rest_resouces for questionaires
    rest_resouces for questions
    rest_resouces for alternative
  ##### namespace /
    rest_resouces for rooms
    rest_resouces for users( criar um user e seta o "cookie de sessão")

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
      alternative_id: '252c3b89-27ab-4fd3-a11c-3d2f5f83f526'
    }

  #### unsubscribed
  Apenas fechar a conexão