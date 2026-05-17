

----------

## **Running the ReqRes API Automation Suite**

### **1: One-Time Setup (Prerequisites)**

Before running the tests, you need following Prerequisites:

1.  **Install Node.js:** * Go to [nodejs.org](https://nodejs.org/) and download the "LTS" (Long Term Support) version for your operating system.
    
    -   Run the installer and accept the default settings.
        
2.  **Install Newman:**
    
    -   Open your computer's Terminal (Mac/Linux) or Command Prompt (Windows).
        
    -   Copy, paste, and run this command:
        
                
        ```
        npm install -g newman
        
        ```
        
3.  **Install the Dashboard Reporter:**
    
    -   To get the visual HTML report, run this second command in your terminal:
        
        
        
        ```
        npm install -g newman-reporter-htmlextra
        
        ```
        

----------

### **2: File Preparation**

You should have received two `.json` files for this test suite:

-   `Reqres_Automation.postman_collection.json` (The test scripts)
    
-   `Reqres_Env.postman_environment.json` (The required variables and API keys)
    

1.  Create a new, empty folder on your Desktop (e.g., name it `API_Tests`).
    
2.  Move **both** `.json` files into this new folder.
    

----------

### **3: Running the Tests**

1.  Open your Terminal or Command Prompt.
    
2.  Navigate to the folder you just created using the `cd` (change directory) command.
    
    -   _Tip: Type `cd` (with a space), drag the folder from your desktop into the terminal window, and press Enter.
        
3.  Copy and paste the following command exactly as written and press Enter:
   
    ```
    newman run Reqres_Automation.postman_collection.json -e Reqres_Env.postman_environment.json -r htmlextra --delay-request 2000
    
    ```
    

**What this command does:**

-   `newman run`: Starts the tool.
    
-   `-e`: Attaches the environment variables (like the Base URL and API Key).
    
-   `-r htmlextra`: Tells Newman to generate a visual HTML dashboard instead of just terminal text.
    
-   `--delay-request 2000`: Adds a 2-second pause between each request so we don't get blocked by the server's rate limits.
    

----------

### **4: Viewing Your Results**

Once the terminal finishes running the command (it should take about 10-12 seconds):

1.  Open your `API_Tests` folder.
    
2.  You will see a newly created folder named **`newman`**. Open it.
    
3.  Inside, double-click the `.html` file. It will open in your default web browser, showing you a complete breakdown of all total iterations, assertions, and passed/failed tests!
