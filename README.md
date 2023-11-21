
import datetime



class SecurityIncident:

    def __init__(self, description, location, timestamp=None):

        self.description = description

        self.location = location

        self.timestamp = timestamp if timestamp else datetime.datetime.now()



class NeighborhoodSecuritySystem:

    def __init__(self):

        self.incident_log = []



    def report_incident(self, description, location):

        incident = SecurityIncident(description, location)

        self.incident_log.append(incident)

        print(f"Incident reported: {description} at {location} on {incident.timestamp}")



    def view_incident_log(self):

        if not self.incident_log:

            print("No security incidents to display.")

        else:

            for i, incident in enumerate(self.incident_log, start=1):

                print(f"Incident {i} - Description: {incident.description}, Location: {incident.location}, Time: {incident.timestamp}")



if __name__ == "__main__":

    neighborhood_system = NeighborhoodSecuritySystem()



    while True:

        print("\nNeighborhood Security Management System")

        print("1. Report Security Incident")

        print("2. View Incident Log")

        print("3. Exit")



        choice = input("Enter your choice (1/2/3): ")



        if choice == "1":

            description = input("Enter incident description: ")

            location = input("Enter incident location: ")

            neighborhood_system.report_incident(description, location)

        elif choice == "2":

            neighborhood_system.view_incident_log()

        elif choice == "3":

            print("Exiting Neighborhood Security Management System.")

            break

        else:

            print("Invalid choice. Please select 1, 2, or 3.")


