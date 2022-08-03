# Module 2: Introduction to Amazon EC2

[AWS Cloud Practitioner Home](https://github.com/pslucas0212/AWS-Cloud-Practioner)

Amazon Elastic Compute Cloude - EC2 - virtual servicers

You don't pay for stop or terminated services
You share the host with with other VMs on the physical machine. This is known as multi-tenancy.  Even with shared resources, the EC2 instances are secure and separate from each other.

You can control configuration  of the EC2 instance
- pick Windows or Linux
- Configure software running on EC2 instance - apps, 3rd party software, databases, etc.
- EC2 instances are resizable - give it more CPU and memory as needed.  Known as vertical scaling up or down
- Control networking making it public accessible or private
- Compute as a service

EC2 follows a launch, connect, use workflow
- Launch pick template with basic config, specify OS, network, storage and security
- Connect to the instance
- Use

### Transcript
In this video, we are going to talk at a high level about a service called Amazon Elastic Compute Cloud or EC2. If you remember from our coffee shop, the employees are a metaphor for the client/server model where a client sends a request to the server; the server does some work, and then sends a response. That example is for the coffee shop. But the same idea applies to other businesses. Your business, whether it be in healthcare, manufacturing, insurance, or delivering video content to millions of users all around the world, are also using this model to deliver products, resources, or data to your end users. And you're going to need servers to power your business and your applications. You need raw compute capacity to host your applications and provide the compute power that your business needs. When you're working with AWS, those servers are virtual. And the service you use to gain access to virtual servers is called EC2. 

Using EC2 for compute is highly flexible, cost effective, and quick when you compare it to running your own servers on premises in a data center that you own. The time and money it takes to get up and running with on-premises resources is fairly high. When you own your own fleet of physical servers, you first have to do a bunch of research to see what type of servers you want to buy and how many you'll need. Then you purchase that hardware up front. You'll wait for multiple weeks or months for a vendor to deliver those servers to you. You then take them to a data center that you own or rent to install them, rack and stack them, and wire them all up. Then you make sure that they are secure and powered up and then they're ready to be used. Only then can you begin to host your applications on top of these servers. The worst part is, once you buy these servers you are stuck with them whether you use them or not. 

With EC2, it's much easier to get started. AWS took care of the hard part for you already. AWS already built and secured the data centers. AWS has already bought the servers, racked and stacked them, and they are already online ready to be used. AWS is constantly operating a massive amount of compute capacity. And you can use whatever portion of that capacity when you need it. All you have to do is request the EC2 instances you want and they will launch and boot up, ready to be used within a few minutes. Once you're done, you can easily stop or terminate the EC2 instances. You're not locked in or stuck with servers that you don't need or want. Your usage of EC2 instances can vary greatly over time. And you only pay for what you use. Because with EC2, you only pay for running instances, not stopped or terminated instances. 

EC2 runs on top of physical host machines managed by AWS using virtualization technology. When you spin up an EC2 instance, you aren't necessarily taking an entire host to yourself. Instead, you are sharing the host with multiple other instances, otherwise known as virtual machines. And a hypervisor running on the host machine is responsible for sharing the underlying physical resources between the virtual machines. This idea of sharing underlying hardware is called multitenancy. The hypervisor is responsible for coordinating this multitenancy and it is managed by AWS. The hypervisor is responsible for isolating the virtual machines from each other as they share resources from the host. This means EC2 instances are secure. Even though they may be sharing resources, one EC2 instance is not aware of any other EC2 instances also on that host. They are secure and separate from each other. 

Luckily, this is not something you, yourself, need to set up. But it's important to know the idea of multitenancy and have a high level understanding of how this works. EC2 gives you a great deal of flexibility and control. Not only can you spin up new servers or take them offline at will, but you also have the flexibility and control over the configuration of those instances. 

When you provision an EC2 instance, you can choose the operating system based on either Windows or Linux. You can provision thousands of EC2 instances on demand. With a blend of operating systems and configurations to power your business' different applications. 

Beyond the OS, you also configure what software you want running on the instance. Whether it's your own internal business applications, simple web apps, or complex web apps, databases or third party software like enterprise software packages, you have complete control over what happens on that instance. EC2 instances are also resizable. You might start with a small instance, realize the application you are running is starting to max out that server, and then you can give that instance more memory and more CPU. Which is what we call vertically scaling an instance. 

In essence, you can make instances bigger or smaller whenever you need to. You also control the networking aspect of EC2. So what type of requests make it to your server and if they are publicly or privately accessible is something you decide. 

We will touch more on this later in the course in detail. Virtual machines are not a new thing. But the ease of provisioning EC2 instances allows for programmers and businesses to innovate more quickly. AWS has just made it much, much easier and more cost effective for you to acquire servers through this Compute as a Service model. There's a lot more to learn about EC2. We talked about virtualization and the types of software you can run on an EC2 instance. But there is more you can configure with EC2 as well.

### Amazon EC2 Instance Types

EC2 Instance type - combine CPU, Storage, networking and ... for different purposes
Instance types
- General puprose - web servers, application servers, small and medium database - balanced compute, memory and networking resources
- Compute Optimized optimized apps that benefit from high-performance processors - web, application and gamiing server - compute intensive application servers
- Memroy Optimized - memory intensive apps
- Accelerated Computing instances - use h/w co-processors and h/w accelarators. - flooating point calcs, graphics apps, data pattern matching
- Storage optimized - high performance locally stored data - OLTP, data wharehouse - measured with (input/output operations per second) IOPS



#### Transcript. 
Now that we've learned about EC2 instances and the crucial role they play in AWS, let's talk about the different types of EC2 instances that are available. Thinking back to our coffee shop analogy, you'll remember that EC2 instances are like our employees and that they serve client requests. If we want to have a cafe that can serve a lot of customers, then we're probably going to need multiple employees, right? And they all can't just be cashiers. We also need someone to make the drinks, someone to handle the food, and maybe someone to do that cool latte art that our customers love so much. Like any business, there are a variety of tasks that need to be done, and they often require different skillsets. 

If we want our business to operate as efficiently as possible, it's important to make sure that an employee's skillset suits their role. In the same way that our coffee shop has different kinds of employees, AWS has different types of EC2 instances that you can spin up and deploy into your AWS environment. 

Each instance type is grouped under an instance family and are optimized for certain types of tasks. Instance types offer varying combinations of CPU, memory, storage, and networking capacity, and give you the flexibility to choose the appropriate mix of resources for your applications. The different instance families in EC2 are general purpose, compute optimized, memory optimized, accelerated computing, and storage optimized. 

General purpose instances provide a good balance of compute, memory, and networking resources, and can be used for a variety of diverse workloads like web service or code repositories. 

Compute optimized instances are ideal for compute-intensive tasks like gaming servers, high performance computing or HPC, and even scientific modeling. 

Similarly, memory optimized instances are good for memory-intensive tasks. Accelerated computing are good for floating point number calculations, graphics processing, or data pattern matching, as they use hardware accelerators. 

And finally, storage optimized are good for, can you guess it? Workloads that require high performance for locally stored data. 

Now, if we map this back to our coffee shop, our cashier becomes a memory optimized EC2 instance, baristas become compute optimized instances, and our latte art employee is an accelerated computing instance type. And there you have it, EC2 instance types.   


### Amazon EC2 Pricing

Multiple billing options:   
- on-demad - pay how long its used - charged by the second or minute - depends on EC2 type.  No prior contracts needed. Not recommend for instances running 1 year or longer
- Savings Plan - low price on EC2 insntance when comitting to a 1 or 3 year contract.  Save up 72%.  Also applies Fargate and AWS Lambda
- Reserve instance - 75% with known usage instance - 1 or 3 year contract.  Three payment options. Up-fromt, partial up-front, no up-front
- Spot instances - use instance when EC2 hits a certain price, can be taken back AWS when pricing dynamically changes
- Dedicated hosts - no shared tenancy

#### Transcript
We talked about EC2 instance types, but you're all probably wondering how much is this gonna cost me? Well, don't fret. For EC2, we have multiple billing options available. 

The first one and the one that most people are familiar with is called On-Demand. What that means is that you only pay for the duration that your instance runs for. This can be per hour or per second, depending on the instance type and operating system you choose to run. Plus, no long-term commitments or upfront payments are needed. This type of pricing is usually for when you get started and want to spin up servers to test out workloads and play around. You don't need any prior contracts or communication with AWS to use On-Demand pricing. You can also use them to get a baseline for your average usage, which leads us to our next pricing option, Savings Plan. 

Savings Plan offers low prices on EC2 usage in exchange for a commitment to a consistent amount of usage measured in dollars per hour for a one or three-year term. This flexible pricing model can therefore provide savings of up to 72% on your AWS compute usage. This can lower prices on your EC2 usage, regardless of instance family, size, OS, tenancy, or AWS region. This also applies to AWS Fargate and AWS Lambda usage, which are serverless compute options that we will cover later in this course. 

Another option is Reserved Instances. These are suited for steady-state workloads or ones with predictable usage and offer you up to a 75% discount versus On-Demand pricing. You qualify for a discount once you commit to a one or three-year term and can pay for them with three payment options: all upfront, where you pay for them in full when you commit; partial upfront, where you pay for a portion when you commit; and no upfront, where you don't pay anything at the beginning. 

The next option is Spot Instances, and they allow you to request spare Amazon EC2 computing capacity for up to 90% off of the On-Demand price. The catch here is that AWS can reclaim the instance at any time they need it, giving you a two-minute warning to finish up work and save state. You can always resume later if needed. So when choosing Spot Instances, make sure your workloads can tolerate being interrupted. A good example of those are batch workloads. 

And finally, we have Dedicated Hosts, which are physical hosts dedicated for your use for EC2. These are usually for meeting certain compliance requirements and nobody else will share tenancy of that host.
Amazon EC2 pricing
With Amazon EC2, you pay only for the compute time that you use. Amazon EC2 offers a variety of pricing options for different use cases. For example, if your use case can withstand interruptions, you can save with Spot Instances. You can also save by committing early and locking in a minimum level of use with Reserved Instances.

### Scaling Amazon EC2

Scalabiltiy and elasticity - shring grow compute resources based on workload.

Autoscaling
- dyanmic scaling responds to changing demand
- Preditive scaling automate scales based on predicted demand
- To scale faster use dyanic and predictive salging together

#### Transcript Part 1
So we have a good idea now on the basics of EC2 and how it can help with any compute needs, like making coffee. Well, like metaphorically making coffee. The coffee represents the, whatever your instance is producing. The next thing we want to talk about is another major benefit of AWS, scalability and elasticity, or how capacity can grow and shrink, based on business needs.

Here is the on-prem data center dilemma. If your business is like 99% of all businesses out in the world, your customer workloads vary over time: perhaps over a simple 24 hour period, or you might have seasons where you're busy, and weeks that are not in demand. If you're building out a data center, the question is, what is the right amount of hardware to purchase? If you buy for the average amount, the average usage, you won't be wasting money on average. But when the peak loads come in, you won't have the hardware to service the customers, especially during the critical moments to expect to be making all your results.

Now, if you buy for the top max load, you might have happy customers, but for most of the year, you'll have idle resources. Which means your average utilization is very low. And I've seen data centers with average utilization under 10%, just out of fear of missing peak demand. So how do you solve the problem on-premises? Well the truth is, you can't. And here's where AWS changes the conversation entirely. 

What if you could provision your workload to exactly the demand, every hour, every day? Well, now you have happy customers, because they can always get the services they want. And you have a happy financial officer because they get the ROI your company needs. 

And here's how it works. Morgan is behind the counter. She's taking orders and we have a decoupled system. Morgan isn't doing all of the work here, so we need somebody making the drinks. It looks like Rudy's up. Now, the first problem I wanna solve, is the idea that we plan for a disaster. There's a great quote by Werner Vogels that says, "Everything fails all the time, so plan for failure and nothing fails." Or in other words, we ask ourselves what would happen if we lost our order taking instance? Well, we'd be out of business until we'd get another person to work the line, sorry, another instance up and running. 

So here is where AWS makes it really simple. Using the same programmatic method we used to create the original Morgan, we can create a second Morgan. So if one fails, we have another one already on the front line and taking orders. The customers never lose service. Well, don't forget about the backend. Let's make our processing instances redundant as well. So that gets our regular operating capacity. We now have a highly available system, with no single point of failure. And as long as the number of customers in line stays the same, we're good. But you know that's gonna change, right? So let's take a look at what's going to happen when we have a rush of customers, an increase in demand.

### Auto Scaling Part 2 

Two way to scale
- Scale up add more power to the machines you are running - vertical scaling
- Scale out - horizontal scaling

By decoupling the system allow you to scale each part of your compute environment individuall 

Create an auto scaling group and define:
- minimum - minimum number of servers to start after definging auto-scaling group
- desired capacity
- maximum capacity - maximum number of EC2 instances 
- You only pay for the instances you are using

#### Transcript
Now there are two ways to handle growing demands. You can scale up, or scale out. Scaling up means adding more power to the machines that are running, which might make sense in a few cases but think about it. When you have an increase in customers, a bigger instance of Morgan really can't take a customer's order any faster. Because that depends on the customer more than Morgan.

"I'll take an espresso. Oh, wait, is that organic? Make it a soy latte? Actually, I don't know. Do you just have tea?"

What we need are, well, more Morgans. Customers? Oh, no! Looks like the processing instances are about to get overloaded. So let's scale them as well.

Obvious question is obvious. How come they are more order taking instances than order makers?

Well, in this case, the amount of work you can get done is still more than the order machines can send your way. You don't have a backlog. So no reason to add more worker instances. This is one of the great things about decoupling the system. You can end up with exactly the right amount of power for each part of your process, rather than over provisioning to solve a separate problem. Okay, looks like we just cleared that rush.

Now here is where AWS really makes a difference to your business. All these extra workers that are sitting around idle, if you don't need them, send them home or stop the instances. Amazon EC2 Auto Scaling. Adds instances based on demand and then decommissions instances when they are no longer needed. This means that every minute of the day, you always have the correct number of instances. Happy customers. Happy CFO. Happy architecture.


### Directing traffic with Elastic Load Balancing

Off the shelf load balancers work great with AWS - Customer operations team will need to manage

Elastic Load Balancing (ELB) - managed service - undifferentiate heavy lifting IT.

ELB runs at regional level and is automaticall Highly Aavailable and automatically scale as need with your EC2 instances. 

ELB can be used for intenal as well as external EC2 instances.  Scale up down front end ELB and backend ELB. 

This supports a true decoupled architecture.  ELB is one type of load balancing for backend processing on EC2 instances


#### Transcript
So we solved the scaling problem with Amazon EC2 Auto Scaling. But now we've got a bit of a traffic problem, don't we? Let's take a look at the situation. When customers come into the coffee shop, right now they have three options for which cashier to talk to to place an order. And oddly enough, most of them are lining up in one line, causing an uneven distribution of customers per line. Even though we have other cashiers waiting to take orders, standing around doing nothing. Customers come in and aren't sure exactly where to route their order. It would help a lot if we added a host to the situation. 

A host stands at the door and when customers come into the coffee shop, they tell them which line to proceed to for placing their order. The host keeps an eye on the cashier's taking orders, and counts the number of people in line each cashier is serving. Then it will direct new customers to the cashier that has the shortest line, that's the least bogged down, thus allowing the lines to be even across cashiers and helping customers be served in the most efficient manner possible. 

The same idea applies to your AWS environment. When you have multiple EC2 instances all running the same program, to serve the same purpose, and a request comes in, how does that request know which EC2 instance to go to? How can you ensure there's an even distribution of workload across EC2 instances? So not just one is backed up while the others are idle sitting by. You need a way to route requests to instances to process that request. What you need to solve this is called load balancing. 

A load balancer is an application that takes in requests and routes them to the instances to be processed. Now, there are many off the shelf load balancers that work great on AWS. And if you have a favorite flavor that already does exactly what you want, then feel free to keep using it. In which case it will be up to your operations team to install, manage, update, scale, handle fail over, and availability. It's doable. Odds are what you really need is just to properly distribute traffic in a high performance, cost-efficient, highly available, automatically scalable system that you can just set and forget. 

Introducing Elastic Load Balancing. Elastic Load Balancing, or ELB, is one of the first major managed services we're going to talk about in this course. And it's engineered to address the undifferentiated heavy lifting of load balancing. To illustrate this point, I need to zoom out a bit here. To begin with, Elastic Load Balancing is a regional construct, and we'll explain more of what that means in later videos. But the key value for you is that because it runs at the Region level rather than on individual EC2 instances, the service is automatically highly available with no additional effort on your part. 

ELB is automatically scalable. As your traffic grows, ELB is designed to handle the additional throughput with no change to the hourly cost. When your EC2 fleet auto-scales out, as each instance comes online, the auto-scaling service just lets the Elastic Load Balancing service know that it's ready to handle the traffic, and off it goes. Once the fleet scales in, ELB first stops all new traffic, and waits for the existing requests to complete, to drain out. Once they do that, then the auto-scaling engine can terminate the instances without disruption to existing customers. 

ELB is not only used for external traffic. Let's look at the ordering tier, and how it communicates with the production tier. Right now, each front end instance is aware of each backend instance. And if a new back end instance comes online, in this current architecture, it would have to tell every front end instance that it can now accept traffic. This is complicated enough with just half a dozen instances. Now imagine you have potentially hundreds of instances on both tiers. Each tier shifting constantly based on demand. Just keeping them networked efficiently is impossible. 

Well, we solve the back end traffic chaos with an ELB as well. Because ELB is regional, it's a single URL that each front end instance uses. Then the ELB directs traffic to the back end that has the least outstanding requests. Now, if the back end scales, once the new instance is ready, it just tells the ELB that it can take traffic, and it gets to work. The front end doesn't know and doesn't care how many back end instances are running. This is true decoupled architecture.
 
There's even more that the ELB can do that we'll learn about later, but this is good enough for now. The key is choosing the right tool for the right job, which is one of the reasons AWS offers so many different services. For example, back end communication. There are many ways to handle it and ELB is just one method. Next, we'll talk about some other services that might work even better for some architectures.


### Messaging and Queueing

Messaging and queueing - applications asynchronously sends messages to a "buffer".  A tightly coupled application requires both apps to be available to send and recieve message.  Asynchronous systems messaging and queueing are loosely coupled.


App A sends message -> to a meassage que <- App B retreives message

Two services availabel on AWS
- SQS (Simple Queue systems)  - send, store, receive messages at any volume .  SQS contain messages untile retreived
- SNS (Simple Notification systems) - this use a pub/sub model - define a topic that subscribers retreive message froms.  Fan out notifcation using mobile SMS, email, mobile push...

#### Transcript
Let's talk about messaging and queuing. In the coffee shop, there are cashiers taking orders from the customers and baristas making the orders. Currently, the cashier takes the order, writes it down with a pen and paper, and delivers this order to the barista. The barista then takes the paper and makes the order. When the next order comes in, the process repeats. This works great as long as both the cashier and the barista are in sync. But what would happen if the cashier took the order and turned to pass it to the barista and the barista was out on break or busy with another order? Well, that cashier is stuck until the barista is ready to take the order. And at a certain point, the order will probably be dropped so the cashier can go serve the next customer. 

You can see how this is a flawed process, because as soon as either the cashier or barista is out of sync, the process will degrade, causing slow downs in receiving orders and failures to complete orders at all. A much better process would be to introduce some sort of buffer or queue into the system. Instead of handing the order directly to the barista, the cashier would post the order to some sort of buffer, like an order board. 

This idea of placing messages into a buffer is called messaging and queuing. Just as our cashier sends orders to the barista, applications send messages to each other to communicate. If applications communicate directly like our cashier and barista previously, this is called being tightly coupled. 

A hallmark trait of a tightly coupled architecture is where if a single component fails or changes, it causes issues for other components or even the whole system. For example, if we have Application A and it is sending messages directly to Application B, if Application B has a failure and cannot accept those messages, Application A will begin to see errors as well. This is a tightly coupled architecture. 

A more reliable architecture is loosely coupled. This is an architecture where if one component fails, it is isolated and therefore won't cause cascading failures throughout the whole system. If we coded the application to use a more loosely coupled architecture, it could look as follows. 

Just like our cashier and barista, we introduced a buffer between the two. In this case, we introduced a message queue. Messages are sent into the queue by Application A and they are processed by Application B. If Application B fails, Application A doesn't experience any disruption. Messages being sent can still be sent to the queue and will remain there until they are eventually processed. 

This is loosely coupled. This is what we strive to achieve with architectures on AWS. And this brings me to two AWS services that can assist in this regard. Amazon Simple Queue Service or SQS and Amazon Simple Notification Service or SNS. But before I dive into those two services, let me just order a to-go coffee on our cafe website. Done. All right, well, that's great. I should get a message when that order is ready. 

First up, let's discuss Amazon SQS. SQS allows you to send, store, and receive messages between software components at any volume. This is without losing messages or requiring other services to be available. Think of messages as our coffee orders and the order board as an SQS queue. Messages have the person's name, coffee order, and time they ordered. The data contained within a message is called a payload, and it's protected until delivery. SQS queues are where messages are placed until they are processed. And AWS manages the underlying infrastructure for you to host those queues. These scale automatically, are reliable, and are easy to configure and use. 

Now, Amazon SNS is similar in that it is used to send out messages to services, but it can also send out notifications to end users. It does this in a different way called a publish/subscribe or pub/sub model. This means that you can create something called an SNS topic which is just a channel for messages to be delivered. You then configure subscribers to that topic and finally publish messages for those subscribers. In practice, that means you can send one message to a topic which will then fan out to all the subscribers in a single go. These subscribers can also be endpoints such as SQS queues, AWS Lambda functions, and HTTPS or HTTP web hooks. 

### Additional Computer Services

- Serverless computing - You dont' see or can't access underlying environment.  AWS manages provisioning, maitnenance and deprovisioingin instances for you

AWS Lambda is a serverless service - you define a trigger, your code runs when the trigger quicks off.  AWS manages the lambda service.  Lambda is for code/services that run less than 15 minutes.
- Upload code to lambda
- Set code to trigger from an event source
- Code only runs when triggered
- Pay for compute time use

Run your code in containers.  
AWS Elastic Container Services (ECS)
- Docker container is a package for your code - code, dependencies and configuration.  Containers run on EC2 instances.  The host is an EC2 instance. ECS supports container orchestration.  Run on top of EC2.  If you dont' care about underlying EC2 instance you can use AWS Fargate - serverless compute platform for ECS and EKS


AWS Elatic Kubernetes services (EKS) - container orchestration running on a cluster.  Orch

Hosting traditional apps and want underlying access to OS - EC2
Host short running services, functions, etc. - use Lambda
Run containers - chose orchestration with ECS or EKS.  Chose if you want to access underlying EC2 instance or want "serverless" support, then use Fargate

#### Transcript

EC2 instances are virtual machines that you can provision with minimal friction to get up and running on AWS. EC2 is great for all sorts of different use cases like running basic web servers to running high performance computing clusters and everything in between. 

That being said, though EC2 is incredibly flexible, reliable, and scalable, depending on your use case, you might be looking at alternatives for your compute capacity. EC2 requires that you set up and manage your fleet of instances over time. When you're using EC2, you are responsible for patching your instances when new software packages come out, setting up the scaling of those instances as well as ensuring that you've architected your solutions to be hosted in a highly available manner. This is still not as much management as you would have if you hosted these on-premises. But management processes will still need to be in place. 

You might be wondering what other services does AWS offer for compute that are more convenient from a management perspective. This is where the term serverless comes in. AWS offers multiple serverless compute options. Serverless means that you cannot actually see or access the underlying infrastructure or instances that are hosting your application. Instead, all the management of the underlying environment from a provisioning, scaling, high availability, and maintenance perspective are taken care of for you. All you need to do is focus on your application and the rest is taken care of. 

AWS Lambda is one serverless compute option. Lambda's a service that allows you to upload your code into what's called a Lambda function. Configure a trigger and from there, the service waits for the trigger. When the trigger is detected, the code is automatically run in a managed environment, an environment you do not need to worry too much about because it is automatically scalable, highly available and all of the maintenance in the environment itself is done by AWS. If you have one or 1,000 incoming triggers, Lambda will scale your function to meet demand. Lambda is designed to run code under 15 minutes so this isn't for long running processes like deep learning. It's more suited for quick processing like a web backend, handling requests or a backend expense report processing service where each invocation takes less than 15 minutes to complete. 

If you weren't quite ready for serverless yet or you need access to the underlying environment, but still want efficiency and portability, you should look at AWS container services like Amazon Elastic Container Service, otherwise known as ECS. Or Amazon Elastic Kubernetes Service, otherwise known as EKS. 

Both of these services are container orchestration tools, but before I get too far here, a container in this case is a Docker container. Docker is a widely used platform that uses operating system level virtualization to deliver software in containers. Now a container is a package for your code where you package up your application, its dependencies as well as any configurations that it needs to run. These containers run on top of EC2 instances and run in isolation from each other similar to how virtual machines work. But in this case, the host is an EC2 instance. When you use Docker containers on AWS, you need processes to start, stop, restart, and monitor containers running across not just one EC2 instance, but a number of them together which is called a cluster. 

The process of doing these tasks is called container orchestration and it turns out it's really hard to do on your own. Orchestration tools were created to help you manage your containers. ECS is designed to help you run your containerized applications at scale without the hassle of managing your own container orchestration software. EKS does a similar thing, but uses different tooling and with different features. 

Both Amazon ECS and Amazon EKS can run on top of EC2. But if you don't want to even think about using EC2s to host your containers because you either don't need access to the underlying OS or you don't want to manage those EC2 instances, you can use a compute platform called AWS Fargate. Fargate is a serverless compute platform for ECS or EKS. That's a bit high level and it might be confusing, so let's clear that up. 

If you are trying to host traditional applications and want full access to the underlying operating system like Linux or Windows, you are going to want to use EC2. If you are looking to host short running functions, service-oriented or event driven applications and you don't want to manage the underlying environment at all, look into the serverless AWS Lambda. If you are looking to run Docker container-based workloads on AWS, you first need to choose your orchestration tool. Do you want to use Amazon ECS or Amazon EKS? After you choose your tool, you then need to chose your platform. Do you want to run your containers on EC2 instances that you manage or in a serverless environment like AWS Fargate that is managed for you? 

Those are just some of your compute options with AWS and it's not even a complete list. Check out the notes for more information on AWS compute services as well as others that we didn't get to talk about in this video.

Additionally, SNS can be used to fan out notifications to end users using mobile push, SMS, and email. Taking this back to our coffee shop, we could send out a notification when a customer's order is ready. This could be a simple SMS to let them know to pick it up or even a mobile push. 
In fact, it looks like my phone just received a message. Looks like my order is ready. See you soon.


### Module Summary

#### Transcript
Hey everyone, I hope you've been enjoying the course so far. We're going to do check-ins like this one after each major topic to review what you've learned. 

First things first, what is cloud computing and what does AWS offer? We define cloud computing as the on-demand delivery of IT resources over the internet with pay-as-you-go pricing. This means that you can make requests for IT resources like compute, networking, storage, analytics, or other types of resources, and then they're made available for you on demand. You don't pay for the resource upfront. Instead, you just provision and pay at the end of the month. 

AWS offers services and many categories that you use together to create your solutions. We've only covered a few services so far, you learned about Amazon EC2. With EC2, you can dynamically spin up and spin down virtual servers called EC2 instances. When you launch an EC2 instance, you choose the instance family. The instance family determines the hardware the instance runs on. 

And you can have instances that are built for your specific purpose. The categories are general purpose, compute optimized, memory optimized, accelerated computing, and storage optimized. 

You can scale your EC2 instances either vertically by resizing the instance, or horizontally by launching new instances and adding them to the pool. You can set up automated horizontal scaling, using Amazon EC2 Auto Scaling. 

Once you've scaled your EC2 instances out horizontally, you need something to distribute the incoming traffic across those instances. This is where the Elastic Load Balancer comes into play. 
EC2 instances have different pricing models. There is On-Demand, which is the most flexible and has no contract, spot pricing, which allows you to utilize unused capacity at a discounted rate, Savings Plans or Reserved Instances, which allow you to enter into a contract with AWS to get a discounted rate when you commit to a certain level of usage, and Savings Plans which apply to AWS Lambda, and AWS Fargate, as well as EC2 instances. 

We also covered messaging services. There is Amazon Simple Queue Service or SQS. This service allows you to decouple system components. Messages remain in the queue until they are either consumed or deleted. Amazon Simple Notification Service or SNS, is used for sending messages like emails, text messages, push notifications, or even HTTP requests. Once a message is published, it is sent to all of these subscribers. 

You also learned that AWS has different types of compute services beyond just virtual servers like EC2. There are container services like Amazon Elastic Container Service, or ECS. And there's Amazon Elastic Kubernetes Service, or EKS. Both of which are container orchestration tools. You can use these tools with EC2 instances, but if you don't want to manage that, you don't need to. 

You can use AWS Fargate, which allows you to run your containers on top of a serverless compute platform. Then there is AWS Lambda, which allows you to just upload your code, and configure it to run based on triggers. And you only get charged for when the code is actually running. No containers, no virtual machines. Just code and configuration. 
Hopefully that sums it up. Catch you in the next one.

