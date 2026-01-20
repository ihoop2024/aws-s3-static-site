# aws-s3-static-site
AWS S3 Static Website 

# Overview
Over the weekend, I built a static website hosted on Amazon S3 to serve as my AWS cloud project portfolio. The goal of this project was to create a simple, cost-effective way to showcase my work while learning how static website hosting works in AWS.
To do this, I created an S3 bucket to store my website files and configured it to allow public read access so the site could be viewed from the internet.

# Prepare website files 
Before touching AWS, I created my website files locally on my machine.
I built the main files (index.html and styles.css) and used generative AI as a development assistant to help structure the layout, styling, and overall design. This allowed me to focus on the AWS configuration and deployment process while still producing a clean, professional-looking site.
<img width="69" height="22" alt="image" src="https://github.com/user-attachments/assets/53ad76e7-7a73-4252-9c54-04a51aee6585" />
<img width="71" height="33" alt="image" src="https://github.com/user-attachments/assets/7a46faa4-d85d-40a0-9032-2b91f806e3ee" />

# Configuration
<img width="679" height="144" alt="image" src="https://github.com/user-attachments/assets/b3bf8aa6-bfd0-44d5-b7a1-c58e8b33fcc8" />



I started by creating an S3 bucket named delonta-s3-portfolio-bucket, making sure the name was globally unique. I selected us-east-1 as the region and left ACLs disabled, following AWS best practices for object ownership

Since S3 blocks public access by default, I intentionally disabled the “Block all public access” setting and acknowledged that the bucket would be publicly accessible. This step was required so external users could view my website.


<img width="705" height="365" alt="image" src="https://github.com/user-attachments/assets/ca2a8f11-1fcb-486d-b7c3-e69f21614313" />


Next, I uploaded my website files (index.html and styles.css) as S3 objects. I created an asset/ folder within the bucket to include my resume on the website. At this point, the files were stored in the bucket but were not yet accessible as a website.


<img width="696" height="291" alt="image" src="https://github.com/user-attachments/assets/185070df-9ecc-41c8-a168-02d6b2599f02" />


To enable hosting, I opened the Properties tab in the S3 bucket, scrolled down to Static website hosting, and clicked Edit. I enabled static website hosting, selected “Host a static website”, and set the index document to index.html. After saving my changes, AWS provided a website endpoint URL, which I copied for testing later.


<img width="319" height="204" alt="image" src="https://github.com/user-attachments/assets/2a5c480d-e78a-44d8-9c0b-75918af1ec3d" />


Finally, I opened the Permissions tab and added a bucket policy that allows public read access to all objects in the bucket. Once the policy was saved, I pasted the website endpoint URL into my browser and successfully viewed my live website.

# Challenges
One challenge I ran into early on was receiving an error when trying to access the website. After retracing my steps, I discovered that S3 object names are case sensitive. My index document was configured as index.html, but the uploaded file had a different capitalization.

Once I updated the file name to ensure both matched exactly (lowercase “i”), the issue was resolved and my site loaded correctly.

This was a great reminder of how small configuration details can have a big impact in cloud environments.

<img width="924" height="356" alt="image" src="https://github.com/user-attachments/assets/9c6ecefc-6a05-4a60-9e05-6944df6aba26" />

<img width="826" height="230" alt="image" src="https://github.com/user-attachments/assets/cee4da01-2e27-48a7-9f0a-d06303694ede" />

<img width="857" height="252" alt="image" src="https://github.com/user-attachments/assets/6f3825e1-204d-4bc9-990e-2371e4b71534" />

<img width="557" height="299" alt="image" src="https://github.com/user-attachments/assets/e7a568c1-9b8a-4c15-960a-72a0073d8044" />



