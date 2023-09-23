# Elevator

The Elevator System is a Django-based project that simulates an elevator system with various functionalities. All you are asked to do is to decide whether the elevator should go up, go down, or stop.

# Usage

The Elevator Control System provides a web-based interface for simulating elevator operations. You can use this interface to:
1. Call elevators from different floors.
2. Select a destination floor.
3. Observe the elevator's movement.

## Architecture

The Elevator System follows a client-server architecture with a Django server as the backend and a client application (not provided) interacting with the server via RESTful APIs. The Django REST Framework (DRF) is used to develop the APIs, and PostgreSQL is used as the database.


The `api's` directory contains the Django views for handling various API endpoints, while the `elevator_system` directory contains the Django project settings and URL configurations. The `elevator` directory contains the Django models and serializers for the Elevator and Request objects.

## Database Modeling

The Elevator System uses a PostgreSQL database to store the elevator and request data. The primary models are `Elevator` and `Request`, with a one-to-many relationship where an elevator can have multiple requests. The `Elevator` model includes fields such as `current_floor`, `current_direction`, `is_operational`, and `is_open`, while the `Request` model includes fields such as `elevator`, `floor`, and `status`.

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

## Libraries and Plugins Used

The Elevator System uses the following libraries and plugins:

- Django: The web framework used to develop the server-side application.
- Django REST Framework: A powerful and flexible toolkit for building Web APIs.
- PostgreSQL: The database management system used for storing elevator and request data.
- Other dependencies specified in the `requirements.txt` file.


