---
author: [Alfresco Documentation, Alfresco Documentation]
audience: 
category: 
option: 
---

# Working with workflows

A workflow is a work procedure and workflow steps represent the activities users must follow in order to achieve the desired outcome. Alfresco provides two different types of workflow: simple and advanced.

Simple workflow is generated by an Alfresco space that has a defined workflow content rule. The content rule dictates how the content entering, leaving, or currently residing in the space is managed.

Advanced workflow is any workflow constructed using the Alfresco embedded workflow engine. You can start an advanced workflow with the Start Advanced Workflow Wizard or as part of Web Content Management \(WCM\). Advanced workflows are defined in your development environment or the [Alfresco Workflow Designer](http://wiki.alfresco.com/wiki/WorkflowAdministration#Process_Designer_developed_Process_Archive).

Alfresco includes two out-of-the-box workflows: **Adhoc Task** \(for assigning a task to a colleague\) and **Review & Approve** \(for setting up review and approval of content\). These are both basic examples of advanced workflows. In both examples, the content items are attached to the workflow.

In WCM, the workflow is configured for a web form associated with the web project and/or workflow configured as part of the overall web project. The Submit process in WCM is a complex example of advanced workflow that moves content through review, approval, and publishing actions.

Tasks resulting from advanced workflow are managed in your personal dashboard \(**My Alfresco**\).

-   **[Implementing a simple workflow](../tasks/tuh-workflow-simple.md)**  
A smart space with a defined workflow content rule generates simple workflow. In a simple workflow, a space is used to represent a step and the workflow is defined as a content rule. The rule specifies the user actions and flow of the content between the spaces. To add complexity to simple workflow you must create rules for other spaces and pass content around from space to space.
-   **[Implementing an advanced workflow](../tasks/tuh-workflow-advanced.md)**  
Advanced workflow allows you to attach workflow directly to a content item and then assign the content to another user for review. With advanced workflow, the workflow tasks are managed in the dashboard.
-   **[Viewing the workflow steps for a content item](../tasks/tuh-workflow-view.md)**  
You can easily determine if a content item is part of a workflow by viewing the content item's details.

**Parent topic:**[Using Alfresco](../concepts/cuh-usingapplication.md)
