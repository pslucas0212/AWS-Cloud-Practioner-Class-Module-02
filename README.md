# Module 2: Introduction to Amazon EC2

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

#### Transcript
We talked about EC2 instance types, but you're all probably wondering how much is this gonna cost me? Well, don't fret. For EC2, we have multiple billing options available. 

The first one and the one that most people are familiar with is called On-Demand. What that means is that you only pay for the duration that your instance runs for. This can be per hour or per second, depending on the instance type and operating system you choose to run. Plus, no long-term commitments or upfront payments are needed. This type of pricing is usually for when you get started and want to spin up servers to test out workloads and play around. You don't need any prior contracts or communication with AWS to use On-Demand pricing. You can also use them to get a baseline for your average usage, which leads us to our next pricing option, Savings Plan. 

Savings Plan offers low prices on EC2 usage in exchange for a commitment to a consistent amount of usage measured in dollars per hour for a one or three-year term. This flexible pricing model can therefore provide savings of up to 72% on your AWS compute usage. This can lower prices on your EC2 usage, regardless of instance family, size, OS, tenancy, or AWS region. This also applies to AWS Fargate and AWS Lambda usage, which are serverless compute options that we will cover later in this course. 

Another option is Reserved Instances. These are suited for steady-state workloads or ones with predictable usage and offer you up to a 75% discount versus On-Demand pricing. You qualify for a discount once you commit to a one or three-year term and can pay for them with three payment options: all upfront, where you pay for them in full when you commit; partial upfront, where you pay for a portion when you commit; and no upfront, where you don't pay anything at the beginning. 

The next option is Spot Instances, and they allow you to request spare Amazon EC2 computing capacity for up to 90% off of the On-Demand price. The catch here is that AWS can reclaim the instance at any time they need it, giving you a two-minute warning to finish up work and save state. You can always resume later if needed. So when choosing Spot Instances, make sure your workloads can tolerate being interrupted. A good example of those are batch workloads. 

And finally, we have Dedicated Hosts, which are physical hosts dedicated for your use for EC2. These are usually for meeting certain compliance requirements and nobody else will share tenancy of that host.
Amazon EC2 pricing
With Amazon EC2, you pay only for the compute time that you use. Amazon EC2 offers a variety of pricing options for different use cases. For example, if your use case can withstand interruptions, you can save with Spot Instances. You can also save by committing early and locking in a minimum level of use with Reserved Instances.
