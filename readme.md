1. Check required tools
Open Terminal in Ubuntu and run:

node -v
npm -v
git --version

If all three show versions, skip to Step 2.

If Git is missing:

sudo apt update
sudo apt install -y git curl

Git’s official Linux install guide lists apt-get install git for Debian/Ubuntu systems, and Node’s official download page recommends nvm-based installation for Node.js.

If Node.js/npm is missing or old, install using nvm:

curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.5/install.sh | bash
source ~/.bashrc

Then install Node:

nvm install 24
nvm use 24

Check again:

node -v
npm -v

The nvm project describes nvm as a Node version manager for POSIX shells like bash, which is suitable for Ubuntu.

2. Clone your project from GitHub
Go to Documents or Desktop:

cd ~/Documents

Clone the project:

git clone https://github.com/MusaibParvez07/MAD-PBL-2026.git

Go inside the project:

cd MAD-PBL-2026

Check files:

ls

You should see:

client  server  readme.md

3. Create .env file again
Your .env file was not uploaded to GitHub because it contains API keys. So you must create it again on the college Ubuntu system.

Run:

cd ~/Documents/MAD-PBL-2026/server
nano .env

Add this:

SPOONACULAR_API_KEY=your_spoonacular_api_key
GROQ_API_KEY=your_groq_api_key
JWT_SECRET=mad_pbl_secret_2026
PORT=3001

Save in nano:

Ctrl + O
Enter
Ctrl + X

Important: replace your_spoonacular_api_key and your_groq_api_key with your real keys.

4. Run backend
In Terminal 1:

cd ~/Documents/MAD-PBL-2026/server
npm install
npm start

Expected output:

Recipe Finder API running at http://localhost:3001
Health check: http://localhost:3001/api/health

Test in browser:

http://localhost:3001/api/health

Keep this terminal open.

5. Run frontend
Open a new terminal.

Run:

cd ~/Documents/MAD-PBL-2026/client
npm install --legacy-peer-deps
npm run dev


6. Final Ubuntu commands to remember
Terminal 1: Backend
cd ~/Documents/MAD-PBL-2026/server
npm start
Terminal 2: Frontend
cd ~/Documents/MAD-PBL-2026/client
npm run dev
