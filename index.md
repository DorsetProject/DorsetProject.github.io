---
layout: default
---

[Dorset](https://github.com/DorsetProject/dorset-framework) is a framework for building intelligent assistants. With Dorset, you can build applications like Siri or Amazon Echo. 

## Agents

Agents provide the intelligence of the application. They answer questions or complete tasks.

### Creating a Local Agent

Local agents are written in Java and implement the [Agent](https://github.com/DorsetProject/dorset-framework/blob/master/core/src/main/java/edu/jhuapl/dorset/agents/Agent.java) interface.
Most agents will extend the abstract class [AbstractAgent](https://github.com/DorsetProject/dorset-framework/blob/master/core/src/main/java/edu/jhuapl/dorset/agents/AbstractAgent.java) which provides convenience functions for working the agent's name and description.

{% highlight java %}
public class EchoAgent extends AbstractAgent {
    private static final String SUMMARY = "Echoes anything submitted";
    private static final String EXAMPLE = "Hello world";

    public EchoAgent() {
        setDescription(new Description("echo", SUMMARY, EXAMPLE));
    }

    @Override
    public AgentResponse process(AgentRequest request) {
        return new AgentResponse(request.getText());
    }
}
{% endhighlight %}
