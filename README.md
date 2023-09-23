# Elevator

The Elevator System is a Django-based project that simulates an elevator system with various functionalities. All you are asked to do is to decide whether the elevator should go up, go down, or stop.

# Usage

The Elevator Control System provides a web-based interface for simulating elevator operations. You can use this interface to:
1. Call elevators from different floors.
2. Select a destination floor.
3. Observe the elevator's movement.

# Each elevator has below capabilities:
● Move Up and Down
● Open and Close Door
● Start and Stop Running
● Display Current Status
● Decide whether to move up or down, based on a list of requests from users.

# Elevator System takes care of:
● Decides which lift to associate which floor.
● Marks which elevator is available or busy.
● Can mark which elevator is operational and which is not.

# Assumptions:
● Number of elevators in the system will be defined by the API to intialise the elevator system
● Elevator System has got only one button per floor.
● So if there are a total of 5 floors, there will be 5 buttons per floor.
● Note that, this doesn't not mimic real world, when you would have a total of 10 buttons for 5
floors ( one for up and one for down)
● Once the elevator reaches its called point, then based on what floor is requested, it moves
either up or down.
● Assume the API calls which make the elevator go up/down or stop will reflect immediately.
When the API to go up is called, you can assume that the elevator has already reached the
above floor.
● The system has to assign the most optimal elevator to the user according to their request.

## Architecture

The Elevator System follows a client-server architecture with a Django server as the backend and a client application (not provided) interacting with the server via RESTful APIs. The Django REST Framework (DRF) is used to develop the APIs, and PostgreSQL is used as the database.


The `api's` directory contains the Django views for handling various API endpoints, while the `elevator_system` directory contains the Django project settings and URL configurations. The `elevator` directory contains the Django models and serializers for the Elevator and Request objects.

## Database Modeling

The Elevator System uses a PostgreSQL database to store the elevator and request data. The primary models are `Elevator` and `Request`, with a one-to-many relationship where an elevator can have multiple requests. The `Elevator` model includes fields such as `current_floor`, `current_direction`, `is_operational`, and `is_open`, while the `Request` model includes fields such as `elevator`, `floor`, and `status`.

# API’s required:
1. Initialise the elevator system to create ‘n’ elevators in the system
2. Fetch all requests for a given elevator
3. Fetch the next destination floor for a given elevator
4. Fetch if the elevator is moving up or down currently
5. Saves user requests to the list of requests for a elevator
6. Mark an elevator as not working or in maintenance
7. Open/close the door.
8. 
## API Contracts

The Elevator System exposes the following APIs:

- `POST /api/elevator/initialize/`: Initializes the elevator system by creating 'n' elevators.
- `GET /api/elevator/{elevator_id}/requests/`: Fetches all requests for a given elevator.
- `GET /api/elevator/{elevator_id}/next_destination/`: Fetches the next destination floor for a given elevator.
- `GET /api/elevator/{elevator_id}/current_direction/`: Fetches whether the elevator is currently moving up or down.
- `POST /api/elevator/{elevator_id}/save_request/`: Saves a user request to the list of requests for a specific elevator.
- `POST /api/elevator/{elevator_id}/set_operational/`: Sets the operational status of an elevator.
- `POST /api/elevator/call/`: Call elevator from an external button.
- `POST /api/elevator/{elevator_id}/door_action/`: Sets the operational status of an elevator.

I have also attached the snapshot of postman api collection.


![django](https://github.com/ADITISAHU1611/mindsproject/assets/92028980/4b474e64-cf5b-4745-ab39-78422b0b5054)


