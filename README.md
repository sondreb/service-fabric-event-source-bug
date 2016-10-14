# service-fabric-event-source-bug
Repo that demonstrates the inability to use inheritance on ServiceEventSource.

Simply clone the repo and hit F5 to run and debug to see the exception occur.

When the ServiceEventSource inherits a base class, the WriteEvent() on the base EventSource throws exception.

Exception details:

`
System.IndexOutOfRangeException was unhandled
  HResult=-2146233080
  Message=Index was outside the bounds of the array.
  Source=mscorlib
  StackTrace:
       at System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore(Int32 eventId, Guid* relatedActivityId, Int32 eventDataCount, EventData* data)
       at System.Diagnostics.Tracing.EventSource.WriteEvent(Int32 eventId, String arg1)
       at Example.ServiceEventSourceBase.ServiceHostInitializationFailed(String exception) in C:\src\github\service-fabric-event-source-bug\src\Example\ServiceEventSource.cs:line 139
       at Example.Program.Main() in C:\src\github\service-fabric-event-source-bug\src\Example\Program.cs:line 33
  InnerException: 
`