# Creating Content using Ibexa Connect and Open AI Assistants

* [Task](#task)
* [Requirements](#requirements)
* [Initial Setup](#initial-setup)
* [How it Works](#how-it-works)

## Task
Main task is to use an *OpenAI Assistant* and Ibexa Connect to create Content from a simple instruction sent to Open AI.
The generated Content can for example be used for demonstration purposes. 

## Requirements
- Access to *OpenAI developer platform* that allows to create a new *OpenAI Assistant*
- Installation of Ibexa DXP 4.6
- Access to Ibexa Connect (see https://doc.ibexa.co/projects/connect/en/latest/general/ibexa_connect/)

## Initial Setup

1. Create Content Types `ai_content` and `ai_task` ( ==> [Download Migration File](ressources/migrations-ai-content-types.yml) ).
2. Create an Open AI assistant that returns `.json` as in [Response Json Scheme](ressources/openai-assistant.schema.json)
<img width="45%" alt="openai-assistant-1" src="https://github.com/user-attachments/assets/b6207c70-0215-425c-a302-438d0f728507" />
<img width="45%"  alt="openai-assistant-response-format" src="https://github.com/user-attachments/assets/3526a04e-2002-4208-a79d-86b57e50fd6e" />

3. Import [Szenario: Create content from AI Assistant](ressources/scenario-content-from-openAI.json) to Ibexa Connect and do neccessary changes for your installation (ie. connect the Szenario to your Ibexa DXP installation and your OpenAI Account).

## How it works

Whenever an `ai_task` containing an instruction for your *Open AI assistant* is created, Ibexa Connect will run the following szenario:
<img width="887" height="275" alt="ibexa-connect-scenarion-content-from-openai" src="https://github.com/user-attachments/assets/d9da35a8-dda9-4556-ac1d-e1af3c0858f0" />

- The instruction from your `ai_task` is send to OpenAI
- The AI Assistant creates `Headline`, `Summary` and `Text` from your instruction
- Open AI generates an `Image` based on the `Summary`
- New `ai_content` Content Object is created, containing the generated `Image`, `Headline`, `Summary` and `Text`.

## Example Task

<img width="70%" alt="ai-task-example" src="https://github.com/user-attachments/assets/132b1acd-21c7-4daf-8977-9d55614c7c75" />

## Generated Content

<img  width="70%"  alt="ai-generated-example" src="https://github.com/user-attachments/assets/77aeaf74-2582-4c5c-8aff-639f7ae66333" />




