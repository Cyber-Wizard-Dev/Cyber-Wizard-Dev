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

# Customized data for Cyber-Wizard-Dev
profile_data = {
    "name": "Cyber Wizard Dev",
    "username": "Cyber-Wizard-Dev",
    "bio": "Passionate about cybersecurity, ethical hacking, and building open-source tools to make the digital world safer.",
    "location": "Digital Realm",
    "website": "https://cyberwizard.dev",
    "repositories": [
        {
            "name": "Network-Scanner",
            "description": "A Python-based tool for scanning and analyzing network vulnerabilities.",
            "technologies": ["Python", "Scapy", "Nmap"]
        },
        {
            "name": "Password-Cracker",
            "description": "A brute-force and dictionary-based password cracking tool for educational purposes.",
            "technologies": ["Python", "Hashlib", "Multithreading"]
        },
        {
            "name": "Malware-Analyzer",
            "description": "A sandbox environment for analyzing and reverse-engineering malware samples.",
            "technologies": ["Python", "Cuckoo Sandbox", "YARA"]
        },
        {
            "name": "Secure-Chat-App",
            "description": "An end-to-end encrypted chat application for secure communication.",
            "technologies": ["JavaScript", "Node.js", "WebSocket", "AES Encryption"]
        },
        {
            "name": "Cyber-Wizard-Toolkit",
            "description": "A collection of cybersecurity tools and scripts for penetration testing.",
            "technologies": ["Bash", "Python", "Metasploit", "Wireshark"]
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
