# RepoWatch

**RepoWatch** is a command-line application designed to monitor and display the recent activity of any GitHub user.  
It fetches and summarizes the latest GitHub events for a specified user, such as pushes, repository creations, pull requests, and more.

## Features

- **Fetch Recent Events:** Retrieve the most recent activities of any GitHub user.
- **Event Summary:** Provides a summary of different types of activities including push events, repository creations, pull requests, issues, and more.
- **Customizable Event Limit:** Users can specify how many recent events to display using a command-line argument.

## Prerequisites

- **Java 11** or higher
- **Maven** (optional, if you plan to build the project using Maven)

## GitHub Token (IMPORTANT)

GitHub limits the number of unauthenticated API requests.  
To avoid rate limiting and ensure smooth usage, you must set a **Personal Access Token (PAT)**.

1. Go to your [GitHub Developer Settings](https://github.com/settings/tokens).
2. Create a **Fine-grained personal access token** with **public repository read access**.
3. Copy the token.

Before running the application, set the token as an environment variable:

**On Linux / Mac / Gitpod / Codespaces:**
```bash
export GITHUB_TOKEN=your_token_here
```

**On Windows (Powershell):**
```powershell
$env:GITHUB_TOKEN="your_token_here"
```

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Deeperr0/RepoWatch.git
   ```

2. Navigate to the project directory:
   ```bash
   cd RepoWatch
   ```

3. Compile the project:
   ```bash
   mvn compile
   ```

## Usage

### Running the Application

You can run the application directly using Maven with the following command:

```bash
mvn exec:java -Dexec.mainClass="org.example.Main" -Dexec.args="<GitHub-username>"
```

By default, this command shows the last 6 events in the user's activity.

### Customizing the Event Limit

You can specify the number of events to display (up to 100) using:

```bash
mvn exec:java -Dexec.mainClass="org.example.Main" -Dexec.args="<GitHub-username> --limit <number-of-events>"
```

## Building and Running the Executable JAR

You can also package the application into a single executable `.jar` file:

1. Build the project:
   ```bash
   mvn clean package
   ```

2. Run the application:
   ```bash
   java -jar target/repowatch.jar <GitHub-username> [--limit <number-of-events>]
   ```

(Replace the `.jar` filename if your Maven `pom.xml` produces a different name.)

## Credits

This project idea was inspired by [roadmap.sh](https://roadmap.sh/projects/github-user-activity).

