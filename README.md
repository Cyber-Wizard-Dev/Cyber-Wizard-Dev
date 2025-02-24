import React from "react";
import DeveloperProfile from "./DeveloperProfile";

function App() {
  // Customized data for Cyber-Wizard-Dev
  const profileData = {
    name: "Cyber Wizard Dev",
    username: "Cyber-Wizard-Dev",
    bio: "Passionate about cybersecurity, ethical hacking, and building open-source tools to make the digital world safer.",
    location: "Digital Realm",
    website: "https://cyberwizard.dev",
    repositories: [
      {
        name: "Network-Scanner",
        description: "A Python-based tool for scanning and analyzing network vulnerabilities.",
        technologies: ["Python", "Scapy", "Nmap"],
      },
      {
        name: "Password-Cracker",
        description: "A brute-force and dictionary-based password cracking tool for educational purposes.",
        technologies: ["Python", "Hashlib", "Multithreading"],
      },
      {
        name: "Malware-Analyzer",
        description: "A sandbox environment for analyzing and reverse-engineering malware samples.",
        technologies: ["Python", "Cuckoo Sandbox", "YARA"],
      },
      {
        name: "Secure-Chat-App",
        description: "An end-to-end encrypted chat application for secure communication.",
        technologies: ["JavaScript", "Node.js", "WebSocket", "AES Encryption"],
      },
      {
        name: "Cyber-Wizard-Toolkit",
        description: "A collection of cybersecurity tools and scripts for penetration testing.",
        technologies: ["Bash", "Python", "Metasploit", "Wireshark"],
      },
    ],
  };

  return (
    <div className="App">
      <h1>GitHub Profile Overview</h1>
      <DeveloperProfile {...profileData} />
    </div>
  );
}

export default App;
import React from "react";

const DeveloperProfile = ({ name, username, bio, location, website, repositories }) => {
  // Get all unique technologies used
  const technologiesUsed = [
    ...new Set(repositories.flatMap((repo) => repo.technologies)),
  ];

  return (
    <div className="profile">
      <h2>{name}</h2>
      <p>
        <strong>Username:</strong> {username}
      </p>
      <p>
        <strong>Bio:</strong> {bio}
      </p>
      <p>
        <strong>Location:</strong> {location}
      </p>
      <p>
        <strong>Website:</strong> <a href={website}>{website}</a>
      </p>

      <h3>Repositories</h3>
      <ul>
        {repositories.map((repo, index) => (
          <li key={index}>
            <strong>{repo.name}:</strong> {repo.description}
            <br />
            <em>Technologies: {repo.technologies.join(", ")}</em>
          </li>
        ))}
      </ul>

      <h3>Technologies Used</h3>
      <p>{technologiesUsed.join(", ")}</p>
    </div>
  );
};

export default DeveloperProfile;
body {
  font-family: Arial, sans-serif;
  background-color: #f4f4f9;
  color: #333;
  margin: 0;
  padding: 20px;
}

.App {
  max-width: 800px;
  margin: 0 auto;
  background: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

h1 {
  text-align: center;
  color: #2c3e50;
}

.profile {
  margin-top: 20px;
}

.profile h2 {
  color: #34495e;
}

.profile p {
  line-height: 1.6;
}

.profile a {
  color: #3498db;
  text-decoration: none;
}

.profile a:hover {
  text-decoration: underline;
}

ul {
  list-style-type: none;
  padding: 0;
}

ul li {
  background: #ecf0f1;
  margin: 10px 0;
  padding: 10px;
  border-radius: 4px;
}
