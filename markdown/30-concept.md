<!-- .slide: data-state="section-break" id="concept" data-timing="40" -->
# What is self-healing?
## and what is it trying to solve?


<!-- .slide: data-state="blank-slide" class="full-screen" id="keep-calm" data-menu-title="Keep Calm" data-timing="40" -->
<img alt="Keep Calm, It Just Works" data-src="images/keep-calm-it-just-works.jpg" />

Note:
Who has ever thought this about OpenStack?


<!-- .slide: data-state="normal" id="definition" data-menu-title="What is self-healing?" data-timing="60" -->
# So what is self-healing?

*   <!-- .element: class="fragment" -->
    More than just HA (High Availability)
*   <!-- .element: class="fragment" -->
    Automatic detection of sub-optimal states
    *   "hard" failures (e.g. NIC failure)
    *   "soft" failures / degradation (e.g. exceeds CPU / RAM threshold)
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
impact their neighbour workloads. <!-- .element: class="fragment" -->

*   <!-- .element: class="fragment" -->
    Monitor data-plane network traffic on compute nodes
*   <!-- .element: class="fragment" -->
    If host traffic exceeds threshold set in policy, <br/>
    live-migrate VMs to another host

Note:

Noisy neighbour scenario


<!-- .slide: data-state="normal" id="use-case-3" data-menu-title="Use case #2" data-timing="40" -->
# Use case #2: reactive healing of hard fault

As a cloud operator, I want to ensure that guest workloads can be
recovered if there is a total failure of network connectivity on the
underlying compute node.  <!-- .element: class="fragment" -->

*   <!-- .element: class="fragment" -->
    Monitor data-plane network interfaces on compute nodes
*   <!-- .element: class="fragment" -->
    If host loses connectivity, <br/>
    migrate VMs to another host

### Already implemented and demonstrated in Sydney and Vancouver! <!-- .element: class="fragment" -->

*   <!-- .element: class="fragment" -->
    [Advanced Fault Management with Vitrage and Mistral](https://www.openstack.org/videos/sydney-2017/advanced-fault-management-with-vitrage-and-mistral)
