<!-- .slide: data-state="section-break" id="concept" data-timing="40" -->
# What is self-healing?
## and what is it trying to solve?


<!-- .slide: data-state="blank-slide" class="full-screen" id="keep-calm" data-menu-title="Keep Calm" data-timing="40" -->
<img alt="Keep Calm, It Just Works" src="images/keep-calm-it-just-works.jpg" />

Note:
Who has ever thought this about OpenStack?


<!-- .slide: data-state="normal" id="HA" data-menu-title="Comparison with HA" data-timing="40" -->
# Is it the same as High Availability?

*   <!-- .element: class="fragment" -->
    Not really
*   <!-- .element: class="fragment" -->
    Includes HA, but it's more than that
*   <!-- .element: class="fragment" -->
    Not just cluster management / load-balancing

Note:

HA typically means

- some kind of cluster manager
    -   managing A/A and A/P resources
    -   like Pacemaker or keepalived
- some kind of load-balancer, e.g. HAProxy or a hardware LB


<!-- .slide: data-state="normal" id="definition" data-menu-title="What is self-healing?" data-timing="40" -->
# So what is self-healing?

*   <!-- .element: class="fragment" -->
    Automatic detection of sub-optimal states
    *   "hard" failures
    *   "soft" failures / degradation
*   <!-- .element: class="fragment" -->
    Can be proactive as well as reactive
*   <!-- .element: class="fragment" -->
    Intelligent, context-aware decision-making
*   <!-- .element: class="fragment" -->
    Automated action to improve system reliability / availability /
    performance

Note:

The lines between hard / soft failures, and between recovery /
optimisation are somewhat blurred.


<!-- .slide: data-state="normal" id="use-case-1" data-menu-title="Use case #1" data-timing="40" -->
# Use case #1: proactive healing of soft fault

As a cloud operator, I want to ensure that guest workloads
have sufficient network performance, and do not negatively
impact their neighbour workloads.

*   <!-- .element: class="fragment" -->
    Monitor data-plane network traffic on compute nodes
*   <!-- .element: class="fragment" -->
    If host exceeds threshold set in policy, <br/>
    live-migrate VMs to another host


<!-- .slide: data-state="normal" id="use-case-2" data-menu-title="Use case #2" data-timing="40" -->
# Use case #2: proactive healing of hard fault

As a cloud operator, I want to ensure that guest workloads
have sufficient network performance, and do not negatively
impact their neighbour workloads.

*   Monitor data-plane network traffic on compute nodes
*   If host exceeds threshold set in policy, <br/>
    *taking health of bonded NICs into account*, <br/>
    live-migrate VMs to another host
*   If one half of bond fails, bonding mode may mean
    capacity is halved.


<!-- .slide: data-state="normal" id="use-case-3" data-menu-title="Use case #3" data-timing="40" -->
# Use case #3: reactive healing of hard fault

As a cloud operator, I want to ensure that guest workloads
can be recovered if there is a total failure of network
connectivity on the underlying host.

*   <!-- .element: class="fragment" -->
    Monitor data-plane network interfaces on compute nodes
*   <!-- .element: class="fragment" -->
    If host loses connectivity, <br/>
    live-migrate VMs to another host

### Already implemented and demonstrated in Sydney! <!-- .element: class="fragment" -->

*   <!-- .element: class="fragment" -->
    [Advanced Fault Management with Vitrage and Mistral](https://www.openstack.org/videos/sydney-2017/advanced-fault-management-with-vitrage-and-mistral)
