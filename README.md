# Dependencies
* python 2.7.x
* Jupyter Notebook (http://jupyter.org/install.html)
* APScheduler 3.0.x (http://apscheduler.readthedocs.io/en/3.0/)
* PyMysql (https://pypi.python.org/pypi/PyMySQL)
* SQLAlchemy for Object Relational Mapping (https://www.sqlalchemy.org/)


# Setting up
Ensure that you have python 2.7.x installed , and python path added to your environment variables. 
You can download and install python at https://www.python.org/downloads/release/python-2713/

You can install all dependies at once (at a go ) by running ``pip install -r requirements.txt`` at the root of the application folder.

Alternatively, you could follow the following steps to install dependencies one after the other;

1. Install Jupyther notebook with the command
    ```bash
         pip install jupyter
2. Install APScheduler with the command
    ```bash
         pip install apscheduler
3. Install PyMysql with the command
    ```bash
         pip install pymysql
4. Install SQLAlchemy with the command
    ```bash
         pip install sqlalchemy



# The Database
The database is a MySQL database. Please install mysql database on your local server or host. 

The API interacts with the database using SQLAchemy ORM.

The API also runs a process, that syncs data from a remotely hosted MySQL database on the AWARE Framework dashboard (https://api.awareframework.com)



## Setting up and running 
To setup and run the API, please follow the following steps

1. Follow the steps in setting up, descbribed above in **Setting up** section, to start with
2. open the command prompt at the root of the application (codes) folder
3. run the command 
    ```bash
        python run.py
4. The command in step 3  will start the FLASK built in web server with the address **http://localhost:5000** , or a similar address. The actual address will be displayed in the command prompt. 
5. The base URL to use to run the API will be **http://localhost:5000/care/** . 
6. You can now send request to the api using a web browser or a rest client like 
    * **postman**(https://www.getpostman.com), 
    * **Restlet Client** (https://restlet.com/documentation/client/user-guide) 


# The API Resources
| Endpoint      | Uniform Interface |Description
| ------------- | -------------     |------------- |
| `/care/handover` *** | `GET` | Returns a list of handover entries
| `/care/handover/<patient_id>` ***  |  `GET` |Returns a list of handover entries for patient with id `patient_id`

**Note:**
All Endpoints marked *** has optional parameters;
* `start` - include entries starting from `start` timestamp
* `end`     -include entries ending at `end` timestamp 
* `grouping` - present data for patients in `DAILY`, `WEEKLY`, `MONTHLY` averages
