Here is a **polished and tailored version** of your README file. I’ve ensured clarity, consistency, and formatting improvements to make it more professional and user-friendly:

---

# **F13 HRMS - Human Resource Management System**

A **Flask-based HRMS** application leveraging **AWS services** (DynamoDB, S3) for efficient employee and resource management. Designed for small to mid-sized organizations to manage users, leaves, and documents seamlessly.

---

## **Features**
- **User Authentication**: Role-based access (Admin and Employee)
- **Employee Management**: Add, edit, and manage employee records
- **Leave Management**: Submit and track leave requests
- **Document Management**: Upload and organize employee-related documents in S3
- **Interactive Dashboard**: Real-time statistics and insights for admins and employees

---

## **Prerequisites**
- **Python**: Version 3.8 or higher
- **AWS Account**: With access credentials for DynamoDB and S3
- **pip**: Python package manager

---

## **AWS Setup**
1. Create an AWS account if you don’t have one.
2. Set up an IAM user with access to:
   - **DynamoDB**
   - **S3**
3. Save your **AWS Access Key** and **Secret Key** for later use.

---

## **Installation**

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/HRMS-Flask.git
   cd HRMS-Flask
   ```

2. **Create a Virtual Environment**:
   ```bash
   python3 -m venv venv
   ```

3. **Activate the Virtual Environment**:
   - On Windows:
     ```bash
     venv\Scripts\activate
     ```
   - On Unix/MacOS:
     ```bash
     source venv/bin/activate
     ```

4. **Install Required Packages**:
   ```bash
   pip install -r requirements.txt
   ```

5. **Set Up AWS Credentials**:
   Create a `.env` file in the project root and add your AWS credentials:
   ```env
   AWS_ACCESS_KEY=your_aws_access_key
   AWS_SECRET_KEY=your_aws_secret_key
   AWS_REGION=your_aws_region
   ```

---

## **Running the Application**

1. **Start the Flask Server**:
   ```bash
   python run.py
   ```

2. Open your browser and access the application at:
   ```
   http://127.0.0.1:5000
   ```

---

## **Default Admin Credentials**
- **Email**: `admin@f13.com`
- **Password**: `admin123`

---

## **File Structure**

```
HRMS-Flask/
├── app/
│   ├── routes/           # Application routes
│   │   ├── auth_routes.py
│   │   ├── dashboard_routes.py
│   │   ├── document_routes.py
│   │   ├── employee_routes.py
│   │   ├── leave_routes.py
│   │   └── __init__.py
│   ├── templates/        # HTML templates
│   │   ├── auth/
│   │   ├── dashboard/
│   │   ├── documents/
│   │   ├── employees/
│   │   ├── leaves/
│   │   └── base.html
│   ├── static/           # Static assets (CSS, JS)
│   │   ├── css/
│   │   └── js/
│   ├── utils/            # Utility scripts
│   │   └── db_setup.py
│   ├── __init__.py
│   └── config.py         # App configuration
├── venv/                 # Virtual environment
├── .env                  # AWS credentials
├── requirements.txt      # Required Python packages
├── run.py                # Application entry point
└── README.md             # Documentation
```

---

## **AWS Resources Created**
When the application runs, the following AWS resources are automatically created:

1. **DynamoDB Tables**:
   - `F13_HRMS_Users`
   - `F13_HRMS_Employees`
   - `F13_HRMS_Leaves`
2. **S3 Bucket**:
   - Stores uploaded documents under `f13-hrms-documents`.

---

## **Usage Workflow**

### For Admins:
1. Log in using the default credentials.
2. Add and manage employee records.
3. Approve/reject leave requests.
4. Manage uploaded documents.
5. Monitor real-time statistics on the admin dashboard.

### For Employees:
1. Log in with credentials provided by the admin.
2. Submit leave requests.
3. Upload necessary documents.
4. View personal dashboards for leave status and other stats.

---

## **Cleanup AWS Resources**
To remove all AWS resources (tables and buckets) created by the application:

```bash
python cleanup.py
```

---

## **Security Notes**
- Change the **default admin password** immediately after setup.
- Ensure employees update their default passwords.
- **Never commit your `.env` file** to GitHub.
- Use HTTPS and proper security groups when deploying to production.

---

## **Development Guide**

### **To Add New Features**:
1. Create new route files in `app/routes/`.
2. Add corresponding templates in `app/templates/`.
3. Update the database schema or logic in `utils/db_setup.py`.

### **To Customize Styles**:
- Modify the CSS files in `app/static/css/`.
- Update the HTML templates as required.

---

## **Troubleshooting**

1. **DynamoDB Tables Not Created**:
   - Verify AWS credentials in `.env`.
   - Ensure correct region is set in `AWS_REGION`.
   - Check IAM permissions.

2. **Login Fails**:
   - Double-check the email and password.
   - Verify user existence in DynamoDB.
   - Clear browser cookies and try again.

---

## **License**
This project is licensed under the [MIT License](LICENSE).

---

## **Contributing**
Contributions are welcome! If you’d like to improve this project, please fork the repository and submit a pull request.

---

## **Contact**
For any questions or support, feel free to reach out:  
**Author**: [Benny pius D]  
**GitHub**: [https://github.com/benny-17](https://github.com/benny-17)
