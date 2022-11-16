### Rotas API REST
  OBS: Todas as rotas menos o create de user precisa ter setado, anteriormente o cookie de sessão
  
  ## namespace administrative
    rest_resouces for questionaires
    rest_resouces for questions
    rest_resouces for alternative

  rest_resouces for rooms
  rest_resouces for users( criar um user e seta o "cookie de sessão")

### Rotas WebSocket
  rota base: "ws://localhost:3000/cable"

  ## subscribe
  enviar mensagem via websocket no formato:

  command: "subscribe",
  identifier: { 
    channel: "RoomsChannel", 
    room_id: "efa85f58-4fdb-4d30-9836-f5a5efe5c4f9"
  }
  
  ## init_game
  enviar mensagem via websocket no formato:

  command: "message",
  identifier: {
    channel: "RoomsChannel",
    room_id: "efa85f58-4fdb-4d30-9836-f5a5efe5c4f9"
  },
  data: {
    action: 'init_game'
  }

  ## show_current_scoreboard
  enviar mensagem via websocket no formato:

  command: "message",
  identifier: {
    channel: "RoomsChannel",
    room_id: "efa85f58-4fdb-4d30-9836-f5a5efe5c4f9"
  },
  data: {
    action: 'show_current_scoreboard'
  }

  ## register_answer
  enviar mensagem via websocket no formato:

  command: "message",
  identifier: {
    channel: "RoomsChannel",
    room_id: "efa85f58-4fdb-4d30-9836-f5a5efe5c4f9"
  },
  data: {
    action: 'register_answer',
    alternative_id: '252c3b89-27ab-4fd3-a11c-3d2f5f83f526'
  }

  ## unsubscribed
  Apenas fechar a conexão