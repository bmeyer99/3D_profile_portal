# 3D Printer Profiles Portal

## Objective
Create a web application where users can share and compare their 3D printer profiles, filament types, and print settings.

## Design Requirements

* Clean minimalist design
* Responsive and mobile-first interface
* Modern design trends and patterns (Material-Design, Bootstrap, Tailwind CSS)
* Intuitive user experience

## Model Attributes

The following attributes will be used to describe each 3D model:

1. **Geometry type**: e.g., solid, shell, mesh
2. **Number of faces**: a high number might indicate complex geometry
3. **Edge length**: average or maximum edge length
4. **Surface area**: total surface area of the model
5. **Volume**: exact volume of the model (e.g., for checking for overhangs)
6. **Aspect ratio**: longest dimension / shortest dimension
7. **Symmetry**: whether the model has any symmetries (e.g., rotational, mirror)
8. **Intricacy**: a measure of how complex or detailed the model is (e.g., number of small features, holes, etc.)
9. **Scale**: the size of the model in relation to other models
10. **Features**:
    * Overhangs: areas where the model extends beyond its base
    * Holes: internal cavities within the model
    * Tunnels: narrow channels or passages through the model
    * Bridges: thin sections connecting two larger parts of the model

## Print Settings

The following attributes will be used to describe each print job:

1. **Infill density**: The percentage of the model's volume that is infilled with material.
2. **Layer height**: The thickness of each layer in the print process.
3. **Wall thickness**: The minimum wall thickness required for a stable print.
4. **Support material usage**: Whether support materials are used, and if so, how much.
5. **Bridge detection**: Similar to long bridge detection, but more general.
6. **Infill pattern**: The type of infill pattern used (e.g., grid, honeycomb, etc.).
7. **Material usage**: The amount of material used for the print, including filament or resin consumption.
8. **Print speed**: The rate at which the printer moves during printing.
9. **Temperature settings**:
    * Bed temperature
    * Nozzle temperature (or multiple nozzle temperatures)
10. **Retraction settings**:
    * Retraction distance
    * Retraction speed
11. **Filament type**:
    * Type of filament used (e.g., PLA, ABS, PETG, etc.)
    * Filament diameter

## Features

### User Profile Management

* Upload and share 3D printer profiles
* Store and display filament types and print settings
* Commenting system (using Disqus or similar library)
* Rating system (using a rating library like StarRating)
* Notification system (using Node-Socket.IO, Pusher, or Socket.io-client)

### Follow System

* Users can follow other users to stay updated on their activity
* Relationship.js or Follow.js for implementing the follow feature

### Profile Attributes

* Capture user-defined attributes for 3D models, such as:
    + Long bridge detection
    + Ironing settings
    + Support material usage
    + Print speed and temperature
* Store these attributes along with the uploaded profile
* Display attribute values in a user-friendly format on the profile page

# Model Complexity Metrics

To quantify the complexity of 3D models, we will use the following metrics:

1. **Solidity Ratio**: Measures the ratio of solid material to total volume in a 3D model.
2. **Surface Area-to-Volume Ratio (SAVR)**: Calculates the surface area of the model divided by its volume.
3. **Hausdorff Dimension**: A mathematical measure of the complexity of an object's boundary or surface.
4. **Minkowski Functionals (MF)**: Numerical invariants that describe the geometry of a 3D model.
5. **Fractal Dimension**: Estimates the self-similarity of a 3D model by analyzing its detailed structure.

We will use libraries such as [Open3D](https://github.com/isl-org/Open3D), [MeshLab](https://www.meshlab.net/), and [CGAL](https://doc.cgal.org/latest/) to calculate these metrics.

## Calculating Model Complexity Scores

To give a score to the intricacy of 3D models, we will normalize the calculated metric values using a linear or non-linear scaling method to be determined.

## Model Complexity Scores for Example Models

| Model | Solidity Ratio | SAVR | Hausdorff Dimension | MF | Fractal Dimension |
| --- | --- | --- | --- | --- | --- |
| Benchy | 0.8 | 10.5 | 1.2 | 0.9 | 1.1 |
| RepRap Logo | 0.6 | 15.2 | 1.5 | 1.0 | 1.3 |

### Image and Video Gallery

* Use PhotoSwipe or similar library for responsive image galleries
* Embed video content using Video.js

### Storage System

* Amazon S3 or Google Cloud Storage for hosting user-uploaded files

### Analysis and Visualization

* Use Plotly or similar library for creating interactive visualizations

## Technical Requirements

* Containerization (Docker) for deploying application containers
* Self-hosting vs cloud hosting (AWS, Google Cloud, Azure)
* Hybrid approach using self-hosted static assets and cloud-hosted dynamic content
* Use of frameworks:
    + Next.js or NestJS for building scalable backend APIs
    + Django or similar framework for building robust applications

## Development Approach

* Iterative development with many small deployments along the way
* No coding until everything is finalized
* Technical decisions will be made as needed, but design decisions should only be made when necessary

## Next Steps

1. Review and finalize all concepts, frameworks, and features.
2. Start implementing containerization using Docker.
3. Set up self-hosting vs cloud hosting infrastructure.
