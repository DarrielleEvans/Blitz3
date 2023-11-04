# Blitz3
![Blitz3 drawio](https://github.com/DarrielleEvans/Blitz3/assets/89504317/d402ebd9-7c81-41cb-bb4d-3f0cc919f920)

## Summary

Our business experiences a surge in traffic during 12 holidays each year, with peak user counts reaching 900 to 1000 users. However, our current infrastructure, which relies on a t2.micro instance, can only handle a maximum of 700 users. This limitation results in missed sales opportunities and provides a subpar user experience.

## Resolution Steps

To address the issue of inadequate capacity during peak holiday periods, we undertook the following steps:

Server Load Analysis: We initiated a load analysis by pinging the server using J-tester to determine how many users were rejected due to the server's limitations.
Documentation of Results: The load analysis provided valuable data regarding rejected users, which served as a baseline for further decision-making.
AWS Resource Research: A thorough examination of AWS resources was conducted to identify solutions to alleviate our capacity limitations.
Selection of Auto Scaling and Application Load Balancer (ALB): After extensive research, it was determined that implementing an Auto Scaling group in conjunction with an Application Load Balancer (ALB) was the most efficient course of action to address the issue.
Testing the Solution: We added an Auto Scaling group and an Application Load Balancer to our infrastructure and conducted a test involving 1000 requests. All 1000 requests received a 200 response code, indicating successful load distribution and handling.
Scheduled Actions: To further optimize our solution, we configured scheduled actions for the Auto Scaling group and the load balancer to activate on the day before each of the 12 holidays. This proactive approach ensures that we are well-prepared to meet increased demand, and customers do not experience delays while waiting for the Auto Scaling to take effect and traffic rerouting, which can consume additional time and resources.

## Economic Benefits

Implementing an Auto Scaling group and an Application Load Balancer offers several economic advantages compared to upgrading to a stronger instance, such as a c5.4xlarge, with more bandwidth:

* Cost Efficiency: Auto Scaling allows us to adjust our resources to match demand dynamically. During the 12 holiday periods, we experienced a significant increase in traffic. By using Auto Scaling, we only incur higher costs during these peak times, effectively doubling our capacity as needed. In contrast, upgrading to a stronger instance would mean paying for the increased power year-round, even when not required.
  
* Resource Optimization: With Auto Scaling and ALB, we can efficiently allocate resources, ensuring that we have the right amount of server capacity precisely when needed. This prevents unnecessary over-provisioning of resources and reduces costs associated with idle capacity.
  
* Scalability: The Auto Scaling group and ALB solution provide the flexibility to easily adapt to changing traffic patterns beyond just the holiday periods. It ensures that our infrastructure remains responsive to varying workloads without manual intervention.
Improved User Experience: By effectively managing increased holiday traffic, we can provide a better user experience, increasing customer satisfaction and potentially higher sales revenue during peak periods.

In conclusion, the decision to implement Auto Scaling and an Application Load Balancer offers a cost-effective and efficient solution to address the capacity limitations during holiday blitzes while also providing scalability and enhancing the overall user experience. This approach aligns with our goal of optimizing resource usage and controlling costs while ensuring peak performance during critical periods.


