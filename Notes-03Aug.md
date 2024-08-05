 # AWS SOLUTION ARCHITECT ASSOCIATE -NOTES
 
 ## 📈CERTIFICATIONS ROUTE 
   
   <p> Understanding the AWS certification path 
Cloud computing has become essential for modern businesses. Amazon Web Services (AWS) is a leading cloud platform offering many tools & services. To validate our cloud expertise, AWS Certifications provide a clear path.

 They  offer two certification tracks.The first progresses from Cloud Practitioner to Associate, then Professional, and finally Specialty certifications. The second path moves from Practitioner to Associate, then Operation, Developer, and finally Specialty. Based on research and tutorials, starting with the Cloud Practitioner, followed by Solutions Architect Associate and Professional, and then DevOps Professional seems to be the most effective approach. This combination covers both development and operations aspects.
Remember, two key factors for certification success , knowledge and practical experience. While knowledge is crucial, hands-on experience with AWS is equally important for problem-solving, troubleshooting, and solution design. Considering this, starting with the Solutions Architect Associate certification might be beneficial as it encompasses a broader understanding of AWS services and also covering the practitioner area as well. Additionally, the market demands individuals with practical AWS experience, making the Solutions Architect Associate a solid foundation for  AWS career.</p> 

### 1.Aws cloud Practitioner
<p>This entry-level certification is designed for individuals who are new to AWS and cloud computing in general, providing a broad overview of AWS services, concepts, and architectural best practices. 

✅`Requirement : 6 month of fundamental aws Cloud & industruial knowledge`
</p>

<h3>2.Aws Solution Architect Associate :</h3> 
<p>The Solutions Architect- Associate certification focuses on designing distributed systems, selecting appropriate AWS services for different scenarios, and understanding architectural best practices. This certification is suitable for individuals involved in designing and deploying scalable, cost-effective solutions on AWS. 

✅`Requirement: one year of experience solving problem, design solution , implementinng on aws ` .</p>

<h3>3. AWS Certified Solutions Architect – Professional</h3> 
The Solutions Architect - Professional certification dives deeper into complex architectural concepts, hybrid architecture, and doing  advanced deployment scenarios.  

✅`Requirment: 2years of comprehensive experience designing ,operating and troubleshooting using  Aws cloud.`



<h2> ANIMAL4LIFE  </h2>
<p>TO UNDERSTAND THE REAL WORD SCENARIO , REQUIRMENT ,GLOBAL INFRASTRUCTURE , PROBELMS THE FACING AND THEIR IDEAL OUTCOMES.  
 
`ANIMAL4LIFE–An animal rescue and awarness organization` 

They are Working for the regional animal care provider & involve in monitering and habitat destructions . 
Globall headquarter in brisbane australia including 100 of staffs with shared opeartions callcentre,admin ,IT admin, sales and marketing etc. 
And 100s of remote worker globally doing planning, research, collecting data ,scientist and technical activist and lobbiysts as well. <p>
<ul>
<li>Their works involve with IOT and large dataset means big data .</li>
<li>They have small datacentre in brisbone that take five rack spaces</li>  
<li>Datacentre was old the always encourge thier customer to migrate asap.</li> 
<li>The have a vendor in sydney that badly implemented on aws pilot/GCP pilot and azure pilot .</li> 
<li>ALL global offices and mobile worker conusme their services from their om-premises datacentre .</li> </ul>

<br>
<br>
<strong> ✨GLOBAL INFRASTRUCTURE</strong>

As shown in the picture Below :

![Screenshot 2024-08-03 205320](https://github.com/user-attachments/assets/00e92695-0ace-4add-bb36-4faa49ccf6bb)
 


###  REQUIREMENTS 
* The need to upload and downlaod the data globally . 
* Chatt and planning software  
* Need to manage large dataset  
* High availiability & scalability 
  

### 🚩Problems : 
Following are the problems such an organization were facing 
<ul> <li>On-premises datacentre ,so hardware failing issue </li>
<li>Need more investment on physical equipment  </li>
<li>They have already bad experienced with aws pilot/azure pilot . </li>
<li>Due to distance like remote workers , performance issue </li> 
<li>Lack of HA and scalibility .</li></ul>

Due to these problem their progressive project was running are stopped and larger social compaign 
halts . 


Such kind of businesses want to achieve , 
### 🥅 IDEAL OUTCOMES : 

1. Fast performnce for all workers   
2. Deploy into new region quickly when needed  
3. Disaster recovery  
4. low cost and scalable  
5. Agility (social compaingn and prog.app like iot and big data ) 


After going through this it become easy to understand real word scenario, what the want to acheive , how their global infra works and key issues .  


## 🔧 AWS PILOT   
A controlled environment where new aws services are tested and validate before implementation.  
### AWS ACCOUNT :  
A container for identities of user and resources, 
To login into aws account  we need NAME +EMAIL +PAYMENT METHOD (CREDITCARD) 
An aws  root account has full access to aws services and not restircted . 
We  have three options in aws free tier  account :  
`Free trials `             ` 12-month free`            ` always free `

We have limited time access to the resources like for ec2 750 hours per month ,5GB free storage for s3, and 750 hours for rds instance and so on .we can see the detail on free-tier details. 

For `PRODACC` we need a special type of email and creditcard. 

We can also create multiple account with one creditcard but email should be unique and different . 
Here we have a trick where we can create multiple account from a single email.  
We just need to put + after domain name .
like  
#### Qazifaisal@gmail.com 
we can use also 
#### Qazifaisal+awsaccount1@gmail.com for second account  
#### Qazifaisal+awsaccount2@gmail.com for third one and so on..
For complex projects and business we need to manage multiple account .  
After logging into the aws general account , we need to choose the regions first . 

## HOW TO CHOOSE REGIONS 
We need to choose the region on the basis of 
#### 1.Latency 
#### 2.Compilance  
#### 3.Services avaliabilty  
#### 4.Pricing

Before finishing up the account setup we have to do one step  

`Awsaccount`> `account`> `edit`> `IAM user and role access to billing infromation`> `activate IAM access`

Once its activated we have access to  billing console. 


If we want to add more identitiies we have a service called IAM . 

We have three types of identities in IAm :
 
`IAM USER` ,  `IAM GROUP ` and  `IAM ROLE`


# FACTOR :
 A single piece of evidence that proves identity 

There are two factor :  
## Single factor authentication 
Means the `username + password ` 
And second we have many factors called multi-factor.  
There are 4 factors when we  login into web application : 

* KNOWLEDGE: something we know , our username and password  
* Possession: something we have, bank card / MFA device  
* INHERENT: something we are, fingerprint, face scan, voice identity  
* Location: physical /Wi-Fi  


### MFA –MULTI-FACTOR AUTHENTICATION:  
It is used for security purpose.  
User have access to our account and can possibly change configurations or delete resources in our aws account.  
So, we want to protect our root account and IAM.  
`MFA = PASSWORD YOU KNOW + DEVICE WE HAVE= SUCCESSFUL LOGIN ` 
We can use a physical or virtual devices for MFA .  
Physical device: `YubiKey `
Virtual MFA devices: google authenticator App, Authy  
MFA generate one time code repeatedly.  


#### BENIFIT:  
If our password leaked /hacked still our account is not compromised. 

##  NOTE:  
When we create MFA for the  user it generate a secret key &  associated information. 
Aws use this both to generate QR code. Where the application generates the code periodically .   
## IMPLEMENTATION:  
GO to aws account `profile > security credentials >scrolldown to MFA ASSIGN>specifyname,select MFA device,setup authenticator app >fill with consecutive code`  .
## CREATING BUDGET:  
It tells us about how to handle basic cost management of AWS account. 
As AWS account   provide three types of offers  

#### FREE TIER :
provide free trials for short period  

####  12-month free:
provide access for 1-year free allocation  

#### Always free 
provide some services that are free always. 
To create budget means we monitor our spends and alerts when approaches to the certain desired percentages. 
 
## ⬇️Implementation:  

Go to `root account` > `billing dashboard`  

It opens the central location of billing console in aws .the console include billing, payments, credits, purchase orders, cost explorer, budget report and so on..

As we activated the billing preferences, we wil recieve the bill through the mail . 


# IAM- IDENTITY AND ACCESS MANAGEMENT 

With IAM we can add other trusted identity into our account.  
 A GLOBAL resilient services.  
A root user account is non-restricted to any services. If we want other identity to fully or limited access to our aws resources we use IAM.  
In IAM we follow a principle called  LEAST PRIVILEGES PRINCIPLE that means “Don’t give more permission than user’s need.

We have different type of identiies : 

## IAM USER : 
 human’s or application need access to our account .people within organization  

## IAM GROUPS:
 collection of related users. DEVELOPERS, HR, FINANCE, ADMIN ETC  

## IAM ROLE : 
granting external access to account used by aws .  

IAM used when number of things are uncertaines.  

## IAM POLICY: 

Users/group have assigned policies in the form of Json documents that define permission . 

Permission defines to access the resource or deny.  

Like an ec2 instance is accessing s3 we create a role. . 

### Conclusion: 

IAM PERFROM THREE JOBS:  

* Manage IDP (identity provider) 
Means we can create, delete users,groups and role  
* AUTHENTICATION those identity :
Prove you are, claim yourself  
* AUTHORIZE:  You are allow or deny to resources.  
No cost at basic. 

# BEST PRACTICES:  

* Don’t use the root account except   for aws account setup 

* One physical user = one aws user  

* Assign users to groups and assign permission to groups  

* Create strong password policy. 

* Enable MFA  

* Never share IAM users and access keys. 

 
   

