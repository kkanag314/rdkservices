# RDK service/Thunder plugin Types

There are two types of plugins in RDK, In-Process plugins, and Out-of-Process plugins.
- In-Process plugins run within the same process as the main application and can access the application's memory directly. Refer to the [In-process plugin creation steps](developerguide/new_plugin_Inprocess.md).
- Out-of-Process plugins run in a separate process from the main application and connect to main WPEFramework application through COM RPC (Unix sockets). Refer to the Out-of-process plugin creation steps (Out of process plugin steps will be available shortly).
- In summary, the choice between In-Process and Out-of-Process plugins depends on the desired trade-off between stability, security, and performance. Out-of-Process plugins are created primarily for stability (any crashes won't bring down the main WPEFramework process) and for resource intensive plugins (browser plugins like WebKitBrowser) that would fit better as a separate process, whereas In-Process plugins are created mainly for performance.

## Thunder Interfaces

 A thunder interface is `JSONRPC` and `COMRPC` interfaces which provides the communication between the `Thunder (WPE Framework)` and `Thunder plugins (RDK Services)`. If thunder plugin is a out of process plugin, then it's having their own thunder interface which will be saved and maintained in a separate repo [Thunder interfaces](https://github.com/rdkcentral/ThunderInterfaces).

For example, `PersistentStore` Plugin has their own Thunder interface called `IStore` and located in this [link](https://github.com/rdkcentral/ThunderInterfaces/blob/master/interfaces/IStore.h).