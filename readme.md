# Reactive BPM

This is a collection of tools to support a reactive BPM approach using [Red Hat Process Automation Manager](https://developers.redhat.com/products/rhpam/overview/). In particular, this repository aims to provide teams a prescriptive approach for transforming [an Event Storm] into executable documentation that will accompany their application at runtime. The approach was described in detail at [Explore DDD 2018](https://www.slideshare.net/JustinHolmes2/visualizing-your-event-storm-in-new-ways). The talk was recorded and will be available soon. 

## Usage

1) [Deploy Process Automation Manager](https://access.redhat.com/documentation/en-us/red_hat_process_automation_manager/7.0/), preferably in OpenShift, thought the details of the implementation should not matter much.
2) Import this project (i.e. https://github.com/rht-labs/reactive-bpm.git) into Business Central using the "Import Project".
3) Build the resulting "Reactive BPM" project
4) Create a new project where you place your process models.
5) Create a dependency in your new project on the ReactiveBPM project.
6) Create your process model, reusing `ReactiveBPM.ReusableSignalCatchingProcess` for each event in the event storm.



## Known Issues

1) `ReactiveBPM.ReusableSignalCatchingProcess` is built using the legacy process editor due to [this issue](https://issues.jboss.org/browse/JBPM-7736). It should only affect end users if they need to modify the sub process.