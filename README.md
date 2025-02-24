class DeveloperProfile:
    def __init__(self, name, username, bio, location, website, repositories):
        self.name = name
        self.username = username
        self.bio = bio
        self.location = location
        self.website = website
        self.repositories = repositories

    def display_profile(self):
        print(f"Name: {self.name}")
        print(f"Username: {self.username}")
        print(f"Bio: {self.bio}")
        print(f"Location: {self.location}")
        print(f"Website: {self.website}")
        print("\nRepositories:")
        for repo in self.repositories:
            print(f"- {repo['name']}: {repo['description']} (Tech: {', '.join(repo['technologies'])})")

    def get_technologies_used(self):
        technologies = set()
        for repo in self.repositories:
            technologies.update(repo['technologies'])
        return list(technologies)

# Example data for your profile
profile_data = {
    "name": "Cyber Wizard Dev",
    "username": "Cyber-Wizard-Dev",
    "bio": "Passionate about coding, cybersecurity, and open-source contributions.",
    "location": "Earth",
    "website": "https://cyberwizard.dev",
    "repositories": [
        {
            "name": "Project Alpha",
            "description": "A cybersecurity tool for network analysis.",
            "technologies": ["Python", "Scapy", "Flask"]
        },
        {
            "name": "Project Beta",
            "description": "An open-source game developed in Unity.",
            "technologies": ["C#", "Unity", "Blender"]
        },
        {
            "name": "Project Gamma",
            "description": "A machine learning model for anomaly detection.",
            "technologies": ["Python", "TensorFlow", "Pandas"]
        }
    ]
}

# Create a profile instance
profile = DeveloperProfile(**profile_data)

# Display profile overview
profile.display_profile()

# Display technologies used
print("\nTechnologies Used:")
print(", ".join(profile.get_technologies_used()))
