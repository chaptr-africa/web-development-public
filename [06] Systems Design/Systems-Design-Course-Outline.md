# Systems Design Curriculum
This course delves into the intricate world of systems design and algorithms, equipping you with the knowledge and skills necessary to create efficient and scalable software solutions. It encompasses understanding the components of systems, different types of system models, and creating design diagrams. Throughout this course, you'll explore various concepts, from distributed systems to load balancing, containerization, cloud computing, and database design.  Below is a breakdown of the course:

## Week 1 & 2: Introduction to Systems Design (With Practical Design Examples)
| Index | Lesson | Content Breakdown | Project/Quiz |
|---|---|---|---|
| 1.1 | Introduction to Systems Design and Software Development Life Cycle (SDLC) | What is System Design? Importance of Systems Design. Components of Systems Design. Introduction to Software Development Life Cycle (SDLC). Overview of different SDLC models (waterfall, iterative, spiral, agile). Different design diagrams (Gantt Chart, Flow Charts, Data Flow Diagrams). Sample interview questions | Create a simple flowchart for an authentication system |
| 1.2 | Introduction to Distributed Systems and Design Fundamentals | Understanding distributed systems. Scalability of distributed systems. Key characteristics of distributed systems. Types of distributed systems. Advantages and Disadvantages. Introduction to Design Fundamentals (Scaling, Caching, Load Balancing). What is scaling, and its types (Horizontal and Vertical). Importance of scaling. What is caching and its types (Server, client, distributed). Types of load balancers. How load balancers work and their pros and cons | |
| 1.3 | Design Fundamentals Continued and Databases | Proxies (Forward and Reverse Proxy). Message Queues. File Systems. Introduction to databases (Relational and Non-Relational). ACID Properties. Database Replication and Partitioning. Normalization. DB Design | Design a file system structure for an e-commerce website where product images and details need to be stored efficiently. |
| 1.4 | Test-Driven Development and Intro to Data Structures | What is Test-Driven Development? Benefits of TDD. Red/Green/Refactor Cycle. Basics of Data Structures and Algorithms. Introduction to key data structures (arrays, linked lists, trees, Stacks and Queues, Graphs) | |
| 1.5 |  |  |  |

## Week 3: Containerization
| Index | Lesson | Content Breakdown | Project/Quiz |
|---|---|---|---|
| 3.1 | Introduction to Microservices and Containers | Introduction to Microservices. Introduction to Cloud Native. Introduction to Containers. Persisting Data | Challenge: Create a simple microservices-based application using containers (e.g., Docker) and deploy it in a cloud-native environment (e.g., Kubernetes) |
| 3.2 | Docker Compose and Kubernetes Concepts | Docker Compose. Container Registries. Kubernetes Concepts. Namespaces. | Challenge: Use Docker compose to set up a multi-container application and deploy it locally. Then push container images to a container registry.) |
| 3.3 | Kubernetes Pods, Selectors, and Workloads | Nodes. Pods. Selectors. Multi Container Pods. | Challenge: Set up a Kubernetes cluster (locally or using a cloud service) and create Pods with multiple containers, using selectors to organize and manage them. |
| 3.4 | Kubernetes Workloads and Services | Nodes. Pods. Selectors. Multi Container Pods. | Challenge: Deploy an application using Kubernetes Workloads and practice updating the application with minimal service disruption. |
| 3.5 | Storage, Scaling, and Observability | Storage & Persistence. Application Settings. Observability. Dashboards and Scaling | End of Week Challenge : Create a complete microservices-based application with containers, deploying it using Kubernetes, configuring application settings and observability, and implementing auto-scaling based on resource usage. |

## Week 4: Cloud Computing
| Index | Lesson | Content Breakdown | Project/Quiz |
|---|---|---|---|
| 4.1 | Introduction to Cloud Computing | What is Cloud Computing? Key Characteristics of Cloud Computing. Advantages and Benefits of Cloud Services. Cloud Service Models (IaaS, PaaS, SaaS). AWS as a Leading Cloud Service Provider | Challenge: Set up an AWS Free Tier Account |
| 4.2 | AWS Services and Solutions | AWS Core Services (EC2, S3, RDS, etc.). Additional AWS Services (Lambda, DynamoDB, Route 53, etc.). Understanding the AWS Global Infrastructure. Pricing Models in AWS | Challenge: Launch an EC2 Instance and Deploy a Sample Website |
| 4.3 | Networking and Security on AWS | AWS Virtual Private Cloud (VPC). Subnets, Route Tables, and Security Groups. Identity and Access Management (IAM). Securing AWS Resources | Challenge: Create an AWS VPC and Set Up Secure Access|
| 4.4 | Scaling and Load Balancing | Auto Scaling in AWS. Load Balancers in AWS. Ensuring High Availability. AWS Well-Architected Framework | Challenge: Configure Auto Scaling and Set Up a Load Balancer|
| 4.5 | Storage and Databases in AWS | Amazon S3 for Object Storage. AWS Relational Database Service (RDS). NoSQL Databases (DynamoDB). Data Backup and Recovery| Challenge: Create an S3 Bucket, Set Up an RDS Database, and Perform Data Backups |

