# Week 4 - OpenFlow Lab

Student ID ending: 4919

## Question 1: Firewall Rules

The first firewall rule did not work because it had the same priority as the existing forwarding rules. After increasing its priority to 40000, the drop rule took precedence.

Blocking h1 to h3 also prevented h3 from successfully pinging h1 because the ICMP echo replies from h1 to h3 were dropped.

## Question 2: Controller Failure

The existing conversation between h1 and h2 continued working because the switch had cached forwarding rules installed by the controller.

The new conversation between h1 and h3 failed because the disconnected controller could not install new forwarding rules.

After 60 seconds of inactivity, the cached rules expired, causing the existing conversation to fail as well.

## Question 3: Secure vs Standalone Mode

I would choose secure mode for a campus network because it maintains centralized network control and prevents uncontrolled forwarding when the controller fails.

The disadvantage is that communication may be disrupted during controller outages.

Standalone mode improves network availability by allowing the switch to fall back to MAC learning, but it may bypass controller-defined security policies.
