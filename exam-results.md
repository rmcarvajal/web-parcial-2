Rosa María Carvajal Cuellar





|REQUESTS|BODY|RESULT|
|-|-|-|
|GET http://localhost:3003/api/reservations|N/A|200|
|GET http://localhost:3003/api/rooms|N/A|200|
|GET http://localhost:3003/api/reservations/1|N/A|200|
|POST http://localhost:3003/api/reservations|{<br />  "purpose": "test room",<br />  "participants": 9,<br />  "roomId": 2<br />}|201|
|POST http://localhost:3003/api/reservations|{<br />  "purpose": "test room",<br />  "participants": "9",<br />  "roomId": 2<br />}|400|
|POST http://localhost:3003/api/reservations|{<br />  "purpose": "Invalid extra property",<br />  "participants": 6,<br />  "roomId": 1,<br />  "status": "cancelled"<br />}|400|
|POST http://localhost:3003/api/reservations|{<br />  "purpose": "Unknown room",<br />  "participants": 6,<br />  "roomId": 999999999<br />}|404|
|PATCH http://localhost:3003/api/reservations/1/cancel|N/A|200|
|GET http://localhost:3003/api/reservations/1|N/A|200|
|PATCH http://localhost:3003/api/reservations/1/cancel|N/A|409|
|PATCH http://localhost:3003/api/reservations/abc/cancel|N/A|400|
|PATCH http://localhost:3003/api/reservations/999999999/cancel|N/A|404|





Test Suites: 2 passed, 2 total

Tests:       3 passed, 3 total

Snapshots:   0 total

Time:        1.36 s, estimated 2 s

