# ai-hackhaton

## Download or Clone the Project

### Option 1: Clone with Git
If you have Git installed, run:

```bash
git clone https://github.com/DreiMiranda/ai-hackhaton.git
```

Then open the cloned directory:

```bash
cd ai-hackhaton
```

### Option 2: Download as ZIP
- Go to the repository page: https://github.com/DreiMiranda/ai-hackhaton
- Click the green "Code" button, then "Download ZIP"
- Extract the ZIP file
- Open the extracted folder in your terminal or file explorer

## Getting Started

### Option 1: Using npm

#### 1. Install npm (Node.js)
If you don't have npm installed, download and install Node.js from the official website:
[https://nodejs.org/](https://nodejs.org/)
This will install both Node.js and npm (Node Package Manager).

#### 2. Install dependencies
Navigate to the `N8N` directory and run:

```bash
npm install
```

This command installs all required packages listed in `package.json`.

#### 3. Start the project
After installing dependencies, start the project with:

```bash
npm start
```

This will launch the application as defined in the `start` script of `package.json`.

---

### Option 2: Using Docker Compose

If you have Docker installed, you can run n8n using Docker Compose:

1. Make sure `docker-compose.yml` is in your project root (see example below).
2. Run:
   ```bash
   docker-compose up -d
   ```
3. Access n8n at [http://localhost:5678](http://localhost:5678).

**Example `docker-compose.yml`:**
```yaml
version: '3.8'

services:
  n8n:
    image: n8nio/n8n:latest
    ports:
      - "5678:5678"
    environment:
      - N8N_PORT=5678
    volumes:
      # Uncomment to persist workflows and data
      # - ./n8n_data:/home/node/.n8n
    restart: unless-stopped
```

---

If you encounter issues, make sure you are in the correct directory (`N8N`) and that Node.js/npm or Docker are installed correctly.

## Troubleshooting: Freeing Up Port 5678

If you get an error that port 5678 is already in use, you can find and kill the process using CMD:

1. **Find the process using port 5678:**
   ```cmd
   netstat -ano | findstr :5678
   ```
   Look for a line with `LISTENING` and note the PID (Process ID) in the last column.

2. **Kill the process by PID:**
   ```cmd
   taskkill /PID <PID> /F
   ```
   Replace `<PID>` with the number you found above.

**Example:**
If the PID is `12345`, run:
```cmd
taskkill /PID 12345 /F
```

If you need to use a different port, see the instructions above for changing the port number.

#dify account creation, and gemini setup instructions

Please click on this link and follow the instructions
https://gamma.app/docs/Account-Creation-9rsn6yar222p14l