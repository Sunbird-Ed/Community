# Design Principle

## Thinking Microservice Architecture

Sunbird is built with micro services thinking, it is not a pre-packaged learning management solution. Rather, It is a set of core microservices which have been unbundled from the functionality or the solution inside of it, to provide very critical core functionality, related to learning, registries, content, attestations, data and so on.

Sunbird contains“microservices” as lego blocks which can be used by a builder of a platform or solution to compose many solutions rapidly, and even rewire them, depending on the context, diversity and needs, rather than rewriting the full technology stack

#### Unbundling for Diversity

As an architect or a developer downloading Sunbird, there are hundreds of API's, which are microservices exposed via API's available for use, these are generalized and micro. Sunbird has unbundled hundreds of microservices in terms of content attestation, data, etc.

An architect or a developer looking at solutioning can leverage Sunbird microservices to reimagine solutions to suit their needs and decide what to do with them. It would be possible to actually compose solutions that are different from that seen in the reference implementation of Sunbird. One can imagine a wide range of usecases as the microservices can be used in many different ways.

Content Microservice - This includes API’s for content creation, or a collection creation, and the concept of the collection is abstracted enough to be able to actually use it in different contexts not just k-12 education. The Collection API or collection micro service can be used to create a textbook around it, or a collection of courses around it. In this case the concept of a course is nothing but an abstract version of collection.

This approach opens up the possibility to imagine diverse solutions and therefore large scale innovation.

#### Loose Coupling for Evolution

Sunbird micro services are not necessarily dependent on each other, one can choose and use any microservice to serve varied needs.

Registry Microservice - The Registry microservice can be used for various purposes, it can be used to build a registry of schools or registry of contributors or any other registry. This can be dome without using anything from the Sunbird content microservice or collections or anything from any other micro services. This decoupling is an integral part of the Sunbird Architecture and composition story, because it is built in a decoupled manner, your ability to reuse parts of it or full of it in any form or fashion gives you combinatorial capability that gives you a lot of possibility in terms of reimagining solutions to suit different needs and contexts.

#### Observability through Emit v Extract

Sunbird microservices are built such that every microservice captures every action and interaction on the platform naturally emits anonymized confidentiality protecting, privacy protecting data stream, automatically, and accumulated through the Sunbird telemetry infrastructure, so that extraction of data is avoided.

Extraction is what is done when telemetry is not built natively into the microservice architecture. The only way to get data out of the system is by extracting from various components and parts of the system. This exercise is time consuming and inefficient and most importantly, if the design of extraction is not well done, there will be serious privacy and confidentiality implications and unanticipated consequences.

Data and Telemetry micro services : Data and telemetry as a microservice is essential to the building, development and growth of a platform. Telemetry essentially is the ability to remotely observe large systems and also the ability of actors in a system to observe smaller actions.

For instance, in the education system it would be the ability to observe what is happening at a school, a district and at a state level through a set of telemetry feeds that are coming through the digital platform. The actors in each of these levels - a school leader, education officer, state administrator need visibility and often have to extract data to get an understanding of what is going on in their network.

Emit vs Extract is an important construct that even as extenders of Sunbird, developers and architects must ensure that the telemetry and emitting architecture is implemented as part of the microservice, not just as an API.

To understand the architecture principles of designing population scale digital infrastructure, listen to Dr Pramod Varma, CTO of EkStep foundation.

{% embed url="https://youtu.be/1S-599usfjc" %}

``\
``
