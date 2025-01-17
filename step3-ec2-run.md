

### Step 1: Set up an EC2 Instance

1. **Connect to your EC2 instance**:

   - Use the following command to connect to your instance (change the IP address):
     ```bash
     ssh -i ~/labsuser.pem ec2-user@192.168.2.16
     ```

### Step 2: Set Up the Environment
1. **Update the package list and install required packages**:
   ```bash
   sudo yum install python3-pip python3 nginx git
   ```
   
2. **Install virtualenv**:
   ```bash
   sudo pip3 install virtualenv
   ```

### Step 3: Set Up the Flask Application
1. **Clone your Flask application repository or create a new one**:
   ```bash
   git clone https://github.com/cmu-mirakle2000/blockchain.git
   cd blockchain
   ```

2. **Create and activate a virtual environment**:
   ```bash
   virtualenv venv
   source venv/bin/activate
   ```

3. **Install dependencies**:
   
   ```bash
   pip install -r requirements.txt
   ```

### Step 4: Configure Gunicorn
1. **Install Gunicorn**:
   ```bash
   pip install gunicorn
   ```

2. **Test Gunicorn with your Flask app**:
   ```bash
     gunicorn --bind 0.0.0.0:8000 app:app
   ```

4. Test your app from another terminal (Change the IP address)

   ```
   curl -X POST http://192.168.2.122:8000/data -H "Content-Type: application/json" -d '{"key": "value"}'
   
   curl http://192.168.145.122:8000/data
   ```

   

