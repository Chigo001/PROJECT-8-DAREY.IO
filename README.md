PROJECT 8

CONFIGURE APACHE AS A LOAD BALANCER
- I spinned up an Ubuntu Server 20.04 EC2 Instance and named it 'project-8-apache-lb'.
- I also opened TCP port 80 on project-8-apache-lb inbound rule in security group.
<img width="1440" alt="Screenshot 2023-01-27 at 12 39 54 PM" src="https://user-images.githubusercontent.com/115854902/215155797-e7a02f02-4f9a-4bd8-8c6f-27ea37df1624.png">
<img width="1440" alt="Screenshot 2023-01-27 at 12 41 51 PM" src="https://user-images.githubusercontent.com/115854902/215155941-2a1d8bed-b378-4b57-9525-2cba26899320.png">
- Next, i installed Apache load balancer on project-8-apache-lb and configured it to point traffic coming to LB to both webservers. I also ensured it was up and running.
<img width="1440" alt="Screenshot 2023-01-27 at 12 45 22 PM" src="https://user-images.githubusercontent.com/115854902/215156886-e244b8c2-83d2-4356-9e85-c89cae39b4de.png">
<img width="1440" alt="Screenshot 2023-01-27 at 12 46 40 PM" src="https://user-images.githubusercontent.com/115854902/215157184-3c7c23d0-d21f-4275-bf5f-63a5fe4d2798.png">
<img width="1440" alt="Screenshot 2023-01-27 at 12 49 22 PM" src="https://user-images.githubusercontent.com/115854902/215157463-93661a2b-f8a4-444b-92ad-404f23d5a3a4.png">
<img width="1440" alt="Screenshot 2023-01-27 at 12 49 55 PM" src="https://user-images.githubusercontent.com/115854902/215157571-a30f9bd6-03a9-469b-bc2d-5a1ebd0a9987.png">
- I also configured load balancing
<img width="1440" alt="Screenshot 2023-01-27 at 6 14 52 PM" src="https://user-images.githubusercontent.com/115854902/215159657-72ee4dc6-451a-41e4-9d43-d0943eb1c595.png">
I verified my configuration worked by accessing my LB public IP address on my browser
<img width="1440" alt="Screenshot 2023-01-27 at 6 05 51 PM" src="https://user-images.githubusercontent.com/115854902/215160132-3a25229a-8602-4753-b0b2-cbfb21cf135a.png">
<img width="1440" alt="Screenshot 2023-01-27 at 6 06 04 PM" src="https://user-images.githubusercontent.com/115854902/215160154-dea115f7-30e1-44e4-9c05-4d12f0fb8b6c.png">
I connected to my web servers and refreshed severally to ensure that both servers receive HTTP GET request from my LB. New records appeared on my server's log file everytime i refreshed.
<img width="1440" alt="Screenshot 2023-01-27 at 6 18 09 PM" src="https://user-images.githubusercontent.com/115854902/215161514-1111a4ed-b1e0-4c84-a2ca-ef7f665ede55.png">

<img width="1440" alt="Screenshot 2023-01-27 at 6 17 59 PM" src="https://user-images.githubusercontent.com/115854902/215161572-9781936a-fbb2-456e-8e06-1e7ec4fab751.png">
So, I configured IP address to domain nam,e mapping for my LB and also updated my LB config file with those names instead of IP addresses.

<img width="1440" alt="Screenshot 2023-01-27 at 6 10 10 PM" src="https://user-images.githubusercontent.com/115854902/215162633-1ea68929-5d9f-4871-9124-a66b86609f9d.png">

<img width="1440" alt="Screenshot 2023-01-27 at 6 14 52 PM" src="https://user-images.githubusercontent.com/115854902/215162694-07f529de-6707-4b1d-ae05-e2925c4bc634.png">

It's important to note that this configuration is only internal and from the backend and it is also local to the LB Server. These names are neither resolvable from other servers internally or from the internet.


