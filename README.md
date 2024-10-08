# OpenAI | Assistants API | File Search Tool 

## Overview

The OpenAI Assistants API File Search Tool is designed to empower assistants with the ability to access and retrieve information from ***uploaded files*** seamlessly without further preparation like embedding, chunking etc. Those documents can be added to ground completion requests.

It augments the Assistant with knowledge from outside its model and allows dynamically providing information in documents on the fly.

Multiple different document types like *.docx, *.pptx, *.txt, *.pdf, *.md etc. are supported and can be easily uploaded.

The example in this repo showcases:

![Overview](./media/img/overview.png)

- Upload of two .txt files with grounding information to an Azure OpenAI instance
- Creation of a `VectorStore` containing the uploaded .txt files
- Creation of an `Assistant` which can suggest preferred restaurants based on the content of the .txt files
- Creation of a `Thread` being aware of the documents within the created `VectorStore`
- Creation of a `Run` which uses the information within the `VectorStore` as grounding information to create a completion. 

## Repo Content

| File | Content | Details |
| ---- | ------- | ------- |
| [setup](./setup/setup.ipynb) | Polyglot note book to setup all necessary Azure resources to run the provided sample | Creates a resource group, an instance of Azure Open AI with a deployed gpt-4o model |
| [file_search_tool_ipynb](./src/file_search_tool.ipynb) | End-to-end sample which uploads two *.txt files with grounding information for an Assistants API run completion.  | Source code is provided in an easy to understand Polyglot note book with step-by-step guidance. A simple Run using the Azure OpenAI Assistants API is created where grounding information is provided within a Thread based on uploaded text files provided in a vector store. |
| [grounding_data](./assets/grounding_data/) | Grounding information for an Assistants API Run | Two files are provided. File one contains fictitious information about a restaurant in Berlin. The second file contains information about restaurant preferences for a specific person  |