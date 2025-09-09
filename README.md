<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: Dhashvanth B</h3>
<h3>Register Number: 212224230064</h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>
<H3>PROGRAM</H3>

```
import random

class MedicinePrescribingAgent:
    def __init__(self):
        self.rooms = {"Room 1": None, "Room 2": None}
        self.performance = 0
        self.current_room = "Room 1"

    def sense_patient(self, room):
        self.rooms[room] = round(random.uniform(97.0, 101.0), 1)
        return self.rooms[room]

    def treat_patient(self, room):
        temp = self.sense_patient(room)
        print(f"Checking {room}... Patient temperature: {temp}°F")
        if temp > 98.5:
            print(f"Treatment given in {room}.")
            self.performance += 1
            self.rooms[room] = 98.4
        else:
            print(f"No treatment needed in {room}.")

    def move_to_other_room(self):
        if self.current_room == "Room 1":
            print("\nMoving from Room 1 to Room 2...")
            self.current_room = "Room 2"
        else:
            print("\nMoving from Room 2 to Room 1...")
            self.current_room = "Room 1"
        self.performance -= 1

    def run(self, steps=2):
        print("Medicine Prescribing Agent Simulation Started\n")
        for step in range(steps):
            self.treat_patient(self.current_room)
            if step < steps - 1:
                self.move_to_other_room()
        print("\nSimulation Complete!")
        print("Final Performance Score:", self.performance)
        print("Environment State:", self.rooms)


agent = MedicinePrescribingAgent()
agent.run(steps=2)


```
<H3>OUTPUT</H3>

<img width="575" height="241" alt="Screenshot 2025-09-09 133407" src="https://github.com/user-attachments/assets/d562b73a-54a1-49ef-bafd-300d2ea040c0" />


<H3>RESULT</H3>

<p>Thus the AI agent is developed successfully.</p>
