Project goal

Store contacts in a MySQL database
Provide HTTP endpoints for CRUD operations (Create, Read, Update, Delete)
Run in Docker containers using Docker Compose
Persist data using Docker volumes


endpoints 

| Method | Endpoint | Description | Request Body | Response |
| :---- | :---- | :---- | :---- | :---- |
| GET | `/contacts` | Get all contacts | None | List of all contacts |
| POST | `/contacts` | Create new contact | Contact data | Success message \+ ID |
| PUT | `/contacts/{id}` | Update existing contact | Updated fields | Success message |
| DELETE | `/contacts/{id}` | Delete contact | None | Success message |



for run my project you need to open cli on your computer and run the next commands: 

'git clone (https://github.com/IsraelErlan/week10_contacts.git)'
'cd week10_contacts'
'docker compose up -d' (make sure that docker installed in your computer)

for getting all contacts:
'curl http://localhost:8000/contacts'

for adding new contact: 
curl -X POST http://localhost:8000/contacts \
-H "Content-Type: application/json" \
-d '{"first_name":"<contact's first name>","last_name":"<contact's last name>","phone_number":"<contact's phone number>"}' 

for update an contact (you can update one field or more): 
curl -X PUT http://localhost:8000/contacts/<contact_id> \
-H "Content-Type: application/json" \
-d '{"<key tahat you want to change his value>": "<new value>"}'

for delete an contact: 
curl -X DELETE http://localhost:8000/contacts/<contact id>


