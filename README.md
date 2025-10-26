# 🧾 Serverless Student Data Management System

A fully serverless web application deployed on **Amazon Web Services (AWS)** for managing student data efficiently and securely.  
The project demonstrates cloud-native deployment using modern serverless services to achieve scalability, security, and cost optimization.

---

## Project Overview
This application allows users to **add and retrieve student records** through a simple web interface hosted on AWS.  
It eliminates traditional server management by using AWS services that automatically scale and operate on a **pay-per-use** model.

---

## Tech Stack
| Service | Role | Description |
|----------|------|-------------|
| **AWS Lambda** | Compute | Executes backend logic for data insertion and retrieval (Python). |
| **Amazon API Gateway** | API Management | Handles HTTP requests and routes them to Lambda. |
| **Amazon DynamoDB** | Database | Stores structured student records (ID, Name, Class, Age). |
| **Amazon S3** | Frontend Hosting | Hosts static website files (HTML, JS). |
| **Amazon CloudFront** | CDN & Security | Delivers HTTPS endpoint, caching, and content protection. |

---

##  Architecture Diagram
<img width="902" height="372" alt="image" src="https://github.com/user-attachments/assets/ea2d5ef0-5614-4667-a217-e36b05fdb848" />


---

##  Key Features
- Fully **serverless architecture**
- **Pay-per-use** compute and storage model
- **Real-time data operations** (Add/View students)
- **Secure access** via HTTPS and Origin Access Control
- **Automatic scaling** with zero infrastructure management

---

##  Deployment Steps

1. **Create DynamoDB Table**
   - Table name: `student_data`
   - Partition key: `student_id`

2. **Deploy Lambda Functions**
   - `insert_student_data` → Handles POST requests  
   - `get_student` → Handles GET requests  

3. **Set Up API Gateway**
   - Create REST API  
   - Integrate POST and GET methods with Lambda functions  

4. **Upload Frontend to S3**
   - Upload `index.html` and `scripts.js`  
   - Update API endpoint URL inside `scripts.js`

5. **Configure CloudFront**
   - Link to S3 as the origin  
   - Enable HTTPS  
   - Restrict direct S3 access using Origin Access Control (OAC)

---

## Testing
- **Lambda Console:** Test JSON event triggers for insert/retrieve functions  
- **API Gateway:** Verify correct response for POST & GET methods  
- **Browser:** Ensure data submission and display work end-to-end

---

##  Security Highlights
- HTTPS enforced through CloudFront  
- Private S3 bucket (accessible only via CloudFront)  
- IAM roles configured with least privilege access (only `PutItem` and `Scan`)

---

##  Author
**Krisha Shah**  
Cloud Computing Project  
*October 2025*

---

## License
This project is licensed under the **MIT License** – feel free to use and modify with credit.





