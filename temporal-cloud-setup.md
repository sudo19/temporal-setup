What is a Worker Process
A Worker Process is responsible for polling a Task Queue, dequeueing a Task, executing your code in response to a Task, and responding to the Temporal Service with the results.

More formally, a Worker Process is any process that implements the Task Queue Protocol and the Task Execution Protocol.

A Worker Process is a Workflow Worker Process if the process implements the Workflow Task Queue Protocol and executes the Workflow Task Execution Protocol to make progress on a Workflow Execution. A Workflow Worker Process can listen on an arbitrary number of Workflow Task Queues and can execute an arbitrary number of Workflow Tasks.
A Worker Process is an Activity Worker Process if the process implements the Activity Task Queue Protocol and executes the Activity Task Processing Protocol to make progress on an Activity Execution. An Activity Worker Process can listen on an arbitrary number of Activity Task Queues and can execute an arbitrary number of Activity Tasks.
Worker Processes are external to a Temporal Service. Temporal Application developers are responsible for developing Worker Programs and operating Worker Processes. Said another way, the Temporal Service (including the Temporal Cloud) doesn't execute any of your code (Workflow and Activity Definitions) on Temporal Service machines. The Temporal Service is solely responsible for orchestrating State Transitions and providing Tasks to the next available Worker Entity.

While data transferred in Event Histories is secured by mTLS, by default, it is still readable at rest in the Temporal Service.
