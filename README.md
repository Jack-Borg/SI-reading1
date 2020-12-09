# Representational State Transfer

## 1. What exactly is REST? How does the context of it fits to the title of the dissertation?

**RE**presentational **S**tate **T**ransfer is a hybrid architectural style for distributed hypermedia systems derived from several of the network-based architectural styles.  
REST provides a set of architectural constraints that, when applied as a whole, emphasizes scalability of component interactions, generality of interfaces, independent deployment of components, and intermediary components to reduce interaction latency, enforce security, and encapsulate legacy systems.

**Client-Server**: separation of concerns is the principle behind the client-server constraint. By separating the user interface from the data storage, we improve the portability of the user interface across multiple platforms and scalability by simplifying the server components. Significant for the Web, the separation allows the components to evolve independantly and therefore supports the internet-scale requirement of muliple organizational domains.

**Stateless**: communication must be stateless, such that each request from client to server must contain all the information necessary to understand the request and can't take advantage of any stored contex on the server, session state is therefore kept entirely on the client.  
This constraint induces the properties of visibility, reliability and scalability. Visibility is improved becasue a monitoring system doesn't have to look beyond a single request in order to determine the request.  
Reliability is improved because it eases the task of recovering from partial faliures.  
Scalability is improved by not having to store state between requests, which allows the server component to quickly free resources and further simplifies implementation beacuse the server doesn't have to manage resource usage across requests.  
The disadvantages are that it may decrease network performance by increasing the repetitive data with each request since that data can't be left on the server in a shared context.  
In addition, placing the application state on the client-side reduces the server's control over consistent application behavior since the application becomes dependent on the correct implemantaion of semantics across muliple client versions.

**Cache**: to improve network efficiency, we add cache constraints. Cache constraints require that the data within a response to a request be implicitly or explicitly labeled as cacheable or non-cacheable. If a response is cacheable then a client cache is given the right to reuse that response data for a later equivalent request.  
The advantage of adding cache constraints is that they have the potential to eliminate some interactions, improving efficiency, scalability, and user-perceived performance by reducing the average latency of interactions.  
The disadvantage is that a cache can decrease reliability if stale data within the cache differs significantly from the data that would have been obtained had the request been sent directly to the server.

**Uniform interface**: The central feature that ditinguishes the REST architectural style from other network-based styles is its emphasis on a uniform interface between components.  
By applying the software engineering principle of generality to the component interface the overall system architecture is simplified and the visibility of interactions is improved.  
Implementations are decoupled from the services they provide which encourages independent evolvability.  
The disadvatage is taht a uniform interface degrades efficiency, since information is transfered in a standardized form rather than one which is specific to an application's needs.  
The REST interface is designed to be efficient for large-grain hypermedia data transfer, optimizing for the common case of the Web, but resulting in an interface that is not optimal for other forms of architectural interaction.  
In order to obtain a uniform interface, muliple architectural constraints are needed to guide the behavior of components.  
REST is definde by four interface constraints: identification of resources; manipulation of resources through representations; selfdescriptive messages; and, hypermedia as the engine of application state.

**Layered System**: in order to further improve behavior for internet-scale requirements, we add layered system constraints. The layered system style allows an architecture to compose of hierarchical layers by constraining component behavior such that each component can't see beyond the immediate layer with which they are interacting.  
By restricting knowledge of the system to a single layer, we place a bound on the overall system complexity and promote substrate independence.  
Layers can be used to encapsulate legacy services and to protect new services from legacy clients, simplifying components by moving infrequently used functionality to a shared intermediary.  
Intermediaries can also be used to improve system scalability by enabling load balancing of services across muliple networks and processors.  
The disadvantage of a layered system is that they add overhead and latency to the processing ad data, reducing user-perceived performance.  
For a network-based system that supports cache constraints, this can be offset by the benefits of shared caching at intermediaries.  
Placing shared caches at the boundaries of an organizational domain can result in significant performance benefits.  
Layers also allow security policies to be enforced on data crossing the organizational boundary.  
The combination of layered system and uniform interface constraints induces architectural properties similar to those of the uniform pipe-and-filter style.  
Although REST interactions is two-way, the large-grain data flows of hypermedia interactions can each be processed lika a data-flow network, with filter components selectively applied to the data stream in order to transform the content as it passes.  
Within REST, intermediary components can actively transform the content of massages becasuse the massages are self-descriptive and their semantics are visible to intermediaries.

**Code-On-Demand**: REST allows client functionality to be extended by downloading and executing code in the form of applets or scripts. This simplifies clients by reducing the number of features required to be pre-implemented.  
Allowing featrues to be downloaded after deployment imporves extensibility but also reduces visibility and is therefore only an optioonal constraint within REST.

## 2. Why is the dissertation considered so important for the software-architectural world?

The dissertation is considered important, because it was through it that the idea of REST was first introduced. 

## 3. Which is the most valuable outcome you personally get from it?

From reading the dissertation i have broadened my understanding of REST.

## 4. How could you implement it in your own practice as a software developer?

I will begin to consider the advantages and disadvanteges before I just blindly choose REST.
