import React from "react";

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

// DeveloperProfile Component
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

// Main App Component
function App() {
  return (
    <div className="App">
      <h1>GitHub Profile Overview</h1>
      <DeveloperProfile {...profileData} />
    </div>
  );
}

export default App;
