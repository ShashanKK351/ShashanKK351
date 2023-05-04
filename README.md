Trip-Planner
A Trip planner management system would play a significant role in planning the perfect trip. The main purpose is to help tourism companies to pre-plan the trip of their customers according to their system access all the details such as tourist places, travelling mode, accommodation etc. this helps the customer to reduce the unnecessary wastage of time and money. So, proposed system maintains centralized repository to make necessary travel arrangements and to retrieve information easily. The system is implemented in MySQL Workbench and Normalization and Dependencies are also handled perfectly.

ENTITY RELATIONSHIP DIAGRAM
An entity relationship model describes interrelated things of interest in a specific domain of knowledge. The ER Diagram of Trip planner Management System is shown below.

![image](https://user-images.githubusercontent.com/122529052/236267367-b5fda356-c9fe-4d97-af0f-04eef03b76a1.png)

RELATIONAL SCHEMA
A relational database schema helps to understand and organize the structure of a database. It is helpful when we design a new database or existing database is modified to incorporate new functionality.

![image](https://user-images.githubusercontent.com/122529052/236267973-4154c0ca-4ac0-4f14-a839-691a77d139c5.png)

![image](https://user-images.githubusercontent.com/122529052/236268009-715d29ce-9003-413b-ac24-d5daad4bad4a.png) ![image](https://user-images.githubusercontent.com/122529052/236268126-dde57c53-595e-419b-8746-783f2043f01b.png)

Travelling mode

• Trains: This entity is useful for travelling the long distances to one city to another city it contains the train ids, train’s name, source etc. this entity further divided into four entities using normalization.

• Buses: This entity is alternate for trains it contains the bus ids, bus’s name, type of buses etc. this entity further divided into four entities using normalization.

• Cabs: This entity is useful for travelling the short distance it contains the cabs ids, cab type, cost etc. this entity further divided into four entities using normalization.

Accommodation

• Hotels: This entity is useful for staying of customers it contains the hotel id, hotel’s name, type etc. this entity further divided into three entities using normalization.

Tourist places

• City: This entity contains list of cities of tourist places it contains the only city’s name.

• Locality: This entity contains list of area of place in respective city it contains the locality’s id, name etc.

• Places: This entity contains list of tourist place in respective area it contains address, name, description etc.

• Restaurants: This entity contains list of restaurants in respective area it contains address, name, type etc.

DEPENDENCIES AND NORMALIZATION

Train

![image](https://user-images.githubusercontent.com/122529052/236268558-e10dae9e-49c4-4032-a156-bfdaf7475abe.png)

Find Candidate Key • Attribute not present any sides: None • Attribute present Only on left side: name, Dep_time, fare, status, seats, hours. • Attribute present Only on right side: id, classId, source, destination, date. • Attribute present both sides: None CK- (id, classId, source, destination, date)+ = R Now decomposed the table into four table for BCNF normalization.

• Train

In this table there is one functional dependency {train_id --> train_name} and the normal form is BCNF.

• TrainDepartureTime • FDs: {train_id, source} ---> departure_time • Normal Form: BCNF • Foreign Key: o train_id from table Train as train_id o city_name from table City as source • TrainReservation • FDs: o {train_id, ClassId, source, destination, Date} ---> fare o {train_id, ClassId, source, destination, Date} ---> train_status o {train_id, ClassId, source, destination, Date} ---> no_of_seats • Normal Form: BCNF • Foreign Key: o {train_id, source} from table TrainDepartureTime as {train_id, source} o city_name from table City as destination • TrainJourneyHours • FDs: o {train_id, source, destination} ---> journey_hours • Normal Form: BCNF • Foreign Key: o {train_id, source} from table TrainDepartureTime as {train_id, source} o city_name from table City as destination


