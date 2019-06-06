# ServiceBusCLI
CLI to send and receive messages from Azure Service Bus
Executables for both windows 10 and ubuntu 18.04 are located in the Executables folder

How to run Service Bus CLI exe.  Use GIT Bash if you are doing the cat method.  Otherwise, you’ll need to do something equivalent in the DOS console or Powershell.  Look through his code and the various command line options will be more obvious.

Run in
ServiceBusCLI/ServiceBusCLI/bin/Release/netcoreapp2.1

dotnet ServiceBusCLI.dll -w -q testqueue -c "Endpoint=sb://azu-eus1-dev-sb-ftg.servicebus.windows.net/;SharedAccessKeyName=ReadWrite;SharedAccessKey=x5e20YLJ3z7sQ+hPEVK5xtPS8+QLSEiflqX7iUNPD8w=" -m "$visit" -u id:6879a3e3-7ef7-4a10-a5fa-4eeee4a8b08e


Attaching a message to a topic example

dotnet ServiceBusCLI.dll -w -t gb_tasktest -c "Endpoint=sb://azu-eus1-dev-sb-ftg.servicebus.windows.net/;SharedAccessKeyName=ReadWrite;SharedAccessKey=x5e20YLJ3z7sQ+hPEVK5xtPS8+QLSEiflqX7iUNPD8w=" -m "$task"


Cat a json file to a variable for the command line:

$ task=`cat ObjectCreatedEvent.json'  --dont forget about the single tick next to the tilda

This command can be used to read an item off a queue to get rid of it.

dotnet ServiceBusCLI.dll -r -q gb-task-ctx-prov -c "Endpoint=sb://azu-eus1-dev-sb-ftg.servicebus.windows.net/;SharedAccessKeyName=ReadWrite;SharedAccessKey=x5e20YLJ3z7sQ+hPEVK5xtPS8+QLSEiflqX7iUNPD8w="
