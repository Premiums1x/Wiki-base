---
concept: jupyter-notebook
entity_type: concept
aliases: []
sources: ["raw\\02-data-science-and-bigdata\\data_science_bigdata.md"]
confidence: high
created_at: 2026-06-24T09:42:16Z
---

## Definition
Jupyter Notebook is an open-source web application that allows users to create and share documents that contain live code, equations, visualizations, and narrative text. It extends the concept of the traditional text editor by enabling interaction with live data and code within the same interface. Jupyter originated from the IPython project and is maintained as part of a community of projects governed by the [Jupyter development team][jupyter-development-team]. It supports multiple languages beyond Python, including R, Scala, and Julia.

## How it works
Jupyter Notebook achieves its functionality through a web-based client-server architecture. The central component is the Jupyter Notebook server, which runs on a user’s machine or a remote server. The server handles execution of code cells, interactive widgets, and data manipulations. The web-based client is a web application that runs in the user’s web browser, handling the rendering and interaction with Notebooks. This client-server model allows for rich, interactive experiences and facilitates collaborative work and sharing of research findings.

The HTML language with embedded JavaScript provides the rendering instructions for textual and visual content within a Notebook. Users create documents in JSON format that specify the layout, cell types (code, markdown, raw, heading), and the metadata of each cell. This format supports the combination of multiple cell types within a single document, enabling narrative text, formula representations, and executable code to be seamlessly interwoven.

### Variants
- **Notebook Deltas**: Extends the traditional approach by introducing a format for tracking and diffing changes within Notebooks, which is particularly useful for version control systems and collaborative editing.
- **Interactive Widgets**: Enhances Jupyter Notebook by adding user interface elements (widgets) that can interact with the code, enabling more sophisticated data exploration and visualization.
- **JupyterLab**: Builds on Jupyter Notebook by offering a more comprehensive development environment with integrated code editing, debugging, and visualization tools.

## Trade-offs
Jupyter Notebook's design choice to rely on the web browser as an interface comes with several trade-offs. While it provides a flexible and portable environment for running code and visualizations, it also poses challenges related to browser memory limitations and the complexity of reproducibility of the analysis session. Moreover, relying on external links and executing code within the browser environment can increase the risk of accidental data leakage or theft if proper security measures are not implemented.

In terms of performance, Jupyter Notebook might be slower compared to standalone Python scripts or optimized computational environments as code runs through the WebSockets protocol connecting the browser and server. This is at the cost of reduced computational efficiency but provides enhanced interactivity and ease of use for data analysis tasks. Additionally, Jupyter Notebook's reliance on specific frameworks and tools, such as [[numpy]][numpy] for numerical data processing and [[pandas]][pandas] for data manipulation, can make it less accessible for users unfamiliar with these libraries, even though they are essential for efficient data management.

Jupyter Notebook's file structure is complex when considering version control, as it stores cells, code outputs, and metadata in a single JSON file. This can complicate integration with version control systems, necessitating the use of utilities like the notebook-deltas[notebook-deltas] extension to manage changes more effectively.

## See also
- [[python]][python] and r[r] as primary languages supported by Jupyter Notebook
- [[numpy]][numpy] and [[pandas]][pandas] for fundamental data processing and manipulation in Notebooks
- jupyter-development-team[jupyter-development-team] for details on the governance and development of the Jupyter ecosystem