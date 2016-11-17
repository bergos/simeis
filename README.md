# Simeis

## Project title

Simeis: Bring neural networks to the next level by empowering developers to feed them easier with more data

## Which problem you are trying to solve and what's your motivation for it?

Deep learning frameworks allow to address many problems in an promising new way.
Neural networks are trained by existing knowledge and reinforcement learning, instead by fixed rules to solve problems.
But it remains a major challenge to prepare and feed data to a network.
A substantial part of resources are allocated for handcrafting transformations for input datasets.

Linked Data allows machines to access data on the Web similar we are using the Web as humans.
Emerging standards and APIs are often built based on the Resource Description Framework (RDF).

Simeis automates the data preparation and feeding steps for deep learning frameworks by employing RDF data.
Separating the dataset from the models allows for finer optimizations during the individual learning steps.
Ultimately we are able to scale the feeding process by the reuse of existing data which allows to speed up and improve solving problems with deep learning techniques.

## How will your project solve that problem?

### Mapping Linked Data to “neural network ready” Linked Data

Linked Data values are either URIs or literals, but neural networks process only float numbers.
The literals can be mapped to float values, parsed as numbers and scaled or used as boolean flags for multiple neurons with a predefined set of values.
URIs can be mapped to floats or can be resolved to find literal values.
This mapping step will be implemented as a JavaScript microservice with a Hydra Hypermedia Linked Data API.
There will be also an API to bypass the HTTP interface, which is required to process large training datasets.
An initial version will provide utils to implement the mapping in a few lines of JavaScript code.
A later version will read the mapping logic from a Linked Data description.

### Mapping Linked Data to neural network inputs and outputs

The “neural network ready” Linked Data still needs to be converted to the input and output format of an machine learning framework.
Most frameworks provide a Python binding.
Therefore NumPy will be used.
A Linked Data description of the model will be used to map the data to NumPy arrays in both directions.
Because the dimensions may vary, the mapping will contain complex loops and should therefore provide utils for easy debugging during development.

### Linked Data description of the model and project

A Linked Data description allows to change the model without changes to the dataset.
Utils for Keras should be developed to generate the description with few additional properties to the model.
There should be also utils to do the Linked Data to neural network input and output mapping.
A project should combine everything.

### Calling Web APIs based on the network results

The output of the network is mapped to match to the structure of a Hydra Hypermedia Linked Data API.
Hydra is the essential building block to make REST APIs machine readable.

## What is the target audience and how will they benefit from the project?

It is a generic framework, therefore there are many use cases.
JavaScript is used wherever it is possible to get it running on all possible devices.
The initial version focuses on Internet of Things driven use cases.
It can easily be run with an own instance and is thus ideal for process private data in a privacy aware manner.
SoLiD users can use their online identity to connect all kinds of personal data.
In the initial use cases, I address home automation, which benefits from machine learning without the need to define rules.
With the increasing number of sensor this will be a must in the long term.
As an example, it can help saving energy in homes and optimize the usage of decentralized energy sources and stores like solar power and bidirectional batteries of electric cars.
But even bigger deployments are possible like controlling the traffic of cities or huge energy networks.
The Internet of Things is not the only target. There are already big datasets in bioinformatics (EMBL-EBI, UniProt, ChEBI, ...), … and generic datasets like Wikidata or DBpedia public available which can be used.
Also non-public datasets can be processed.
Medical records could be analyzed to align medication to genetics.
In general, the lower entry barrier allows domain experts to join the deep learning world.
The clear separation of the dataset and model allows to improve each piece independently.
Decentralized datasets and models, which are easy to fork, extend and rearrange, will have an impact on deep learning in perspective of quality, quantity and speed of development, like we noticed in open source development when easy to use distributed version control systems became mainstream.

## Did you already work on your idea? What’s the current state and what will be new?

I have worked on different neural networks, e.g. predict protein small molecule bindings and for MIDI music creation.
My work also covers Hydra APIs and in general Linked Data for many different use cases.
Accesing the data using Linked Data technology is a key requirement.
I’m an active member of the W3C Hydra CG, co-chair of the W3C RDFJS CG Representation Task Force [1], contributor to the W3C Web of Things IG and work on Web of Things projects [2][3].
I’m running already a Linked Data home automation setup.
The rules are implemented in JavaScript code and use already generic frameworks for Linked Data Web APIs.

With Simeis I will empower the deep learning community to feed linked data with ease to neural networks.
This will help to scale the input process and speed up the iteration for the generation of usable networks.


[1] https://github.com/rdfjs/representation-task-force
[2] https://github.com/bergos/dark-horse-server
[3] https://github.com/bergos/smallhydra
