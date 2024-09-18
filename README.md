<h1>ExpNo 1: Developing AI Agent with PEAS Description</h1>
<h3>Name: Abdur Rahman Basil A H</h3>
<h3>Register Number: 212223040002</h3>

<h3>AIM:</h3>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>

<h3>Theory</h3>
<h3>Medicine Prescribing Agent:</h3>
<p>This agent prescribes medicine for fever (temperature greater than 98.5 degrees), which we consider as unhealthy, based on the user's temperature input. The environment includes rooms in the hospital (two rooms). The agent must consider two factors: one is the room location, and the other is the presence of an unhealthy patient in a random room. The agent must move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance for each treatment and decrementing it for each movement. Thus, the agent prescribes medicine to unhealthy patients.</p>

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
    <td><strong>Medicine Prescribing Agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
    <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>

<hr>

<h3>DESIGN STEPS</h3>
<h3>STEP 1: Identifying the Input:</h3>
<p>Temperature from patients, Location.</p>

<h3>STEP 2: Identifying the Output:</h3>
<p>Prescribe medicine if the patient in a random room has a fever.</p>

<h3>STEP 3: Developing the PEAS Description:</h3>
<p>The PEAS description is developed by defining the performance, environment, actuators, and sensors in an agent.</p>

<h3>STEP 4: Implementing the AI Agent:</h3>
<p>Treat unhealthy patients in each room and check for unhealthy patients in random rooms.</p>

<h3>STEP 5: Measuring the Performance Parameters:</h3>
<p>For each treatment, performance is incremented. For each movement, performance is decremented.</p>

<h3>PROGRAM</h3>
<pre>
<code>
import random

class HealthMonitoringAgent:
    def __init__(self, patient_data):
        self.patient_data = patient_data
        self.sensors = None
        self.actuators = None

    def monitor_health(self):
        while True:
            current_health_state = self.sensors.get_health_state()
            action = self.choose_action(current_health_state)
            self.actuators.perform_action(action)
            if action == "No specific action needed":
                break

    def choose_action(self, current_health_state):
        # Example: A simple rule-based system for decision-making
        if current_health_state['heart_rate'] > 120:
            return "Alert healthcare provider: High heart rate detected"
        elif current_health_state['blood_pressure'] > 140:
            return "Alert healthcare provider: High blood pressure detected"
        elif current_health_state['temperature'] > 38:
            return "Recommend rest and monitor temperature"
        else:
            return "No specific action needed"

class HealthSensors:
    def get_health_state(self):
        # Example: Simulate health data retrieval (replace with real data in a practical scenario)
        return {
            'heart_rate': random.randint(60, 150),
            'blood_pressure': random.randint(90, 160),
            'temperature': random.uniform(36.0, 38.5)
        }

class HealthActuators:
    def perform_action(self, action):
        # Example: Print or log the action (in a real scenario, this might involve more complex actions)
        print(action)

if __name__ == "__main__":
    patient_data = {'patient_id': 123, 'name': 'John Doe', 'age': 35}
    
    health_sensors = HealthSensors()
    health_actuators = HealthActuators()
    
    health_monitoring_agent = HealthMonitoringAgent(patient_data)
    health_monitoring_agent.sensors = health_sensors
    health_monitoring_agent.actuators = health_actuators
    
    health_monitoring_agent.monitor_health()
</code>
</pre>
