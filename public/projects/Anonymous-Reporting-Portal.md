# Anonymous Reporting Portal
This was a project of the Curricular Unit Projeto III of the course Informatics Engineering at the School of Technology and Management (ESTG-IPVC). This project was carried out by me and my colleague [José Cruz](https://www.linkedin.com/in/jos%C3%A9-cruz-98a8a32b8/).

<small><strong><em>Note: As this project was developed under a Non-Disclosure Agreement (NDA), only partial aspects of the project are presented here.</em><small><strong>

---
##  Project Overview

The **Anonymous Reporting Portal** is a secure web platform developed to facilitate **anonymous complaint submissions** related to legal, ethical, and consumer issues. It aims to **protect the identity** of users while ensuring **compliance** with EU directives like **Directive (EU) 2019/1937**. 

**Key features include:**
- Anonymous report submission
- Real-time complaint categorization
- *Automatic file metadata removal*
- Microservice-based architecture
- Role-based access and dashboards

---

##  Architecture Overview

The system follows a **microservices architecture** to ensure modularity and scalability. Each domain, users, authentication, complaints, metadata processing, is encapsulated in its own container and orchestrated using Docker.

### High-Level Architecture
![High Level Architecture](/projects/AnonymousReportingPortal/High-Level-Architecture.png)
						*Actual image from project slides/report*
### Architecture Diagram

![Architecture Diagram](/projects/AnonymousReportingPortal/architecture-diagram.png)
					*Client ⇌ API Gateway ⇌ Microservices ⇌ Supabase*

---

## Metadata Removal Feature

One of the core privacy safeguards is the **automatic removal of metadata** from uploaded files, including PDFs and images. This ensures the **anonymity of the denunciator** by cleaning hidden file properties such as author, device, or location.
###  Metadata Before Removal

![Metadata Before Removal](/projects/AnonymousReportingPortal/Metadata_before.png)
				*Example showing sensitive fields like "Author", "Device", etc.*
### Metadata After Removal

![Metadata After Removal](/projects/AnonymousReportingPortal/Metadata-After-Removal.png)
					*All identifiable metadata is stripped automatically.*
				
This is handled server-side using tools like **ExifTool**, **Sharp**, and **pdf-lib**, seamlessly integrated into the backend file processing microservice.

---

## Application Interface Snapshots


### Landing & Company Pages

![Landing Pages](/projects/AnonymousReportingPortal/LandingPage.png)
						*Home interface for anonymous users*

![Company Pages](/projects/AnonymousReportingPortal/CompanyPage.png)
						*Search and browse registered companies*

*Note: All companies shown in the demonstration images are fictional and used for illustrative purposes only.*
### Complaint & Denunciation Interfaces

![ComplaintPage](/projects/AnonymousReportingPortal/ComplaintPage.png)
						*Form for anonymous complaint submission*

![Compalint Company Page](/projects/AnonymousReportingPortal/ComplaintCompanyPage.png)
						*User and company can view and respond to entries*

---

##  Technologies Used

- **Frontend:** Next.js, TypeScript
- **Backend:** Express.js (Node), Docker
- **Database & Auth:** Supabase
- **Metadata Removal:** ExifTool, Sharp, pdf-lib
- **Project Management:** GitHub, ClickUp

---

##  Final Thoughts

This project demonstrates a **privacy-focused** approach to whistleblowing systems, prioritizing secure and anonymous communication. The **metadata sanitization pipeline** was one of the most critical and technically demanding features, reflecting the team’s commitment to compliance and security.
