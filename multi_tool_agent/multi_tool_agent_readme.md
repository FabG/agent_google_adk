## Multi Tool Agent

This example showcases an agent built with Google ADK who can answer user questions about the time and weather in a city.

![multi-tool_flow](../images/multi_tool_agent-flow-tool.png)

Your agent's ability to understand user requests and generate responses is powered by a Large Language Model (LLM). 
In this example, we are using Google `gemini-2.0-flash`


### How to run the agent
To run, change the API_Key to yours in `.venv` file
```shell
GOOGLE_GENAI_USE_VERTEXAI=FALSE
GOOGLE_API_KEY=PASTE_YOUR_ACTUAL_API_KEY_HERE
```

Using the terminal, navigate to the parent directory of your agent project (e.g. using cd ..):
```shell
parent_folder/      <-- navigate to this directory
    multi_tool_agent/
        __init__.py
        agent.py
        .env
```

Run the following command, to chat with your Weather agent.

```shell
adk run multi_tool_agent
```
To exit, use Cmd/Ctrl+C.


📝 Example prompts to try¶
-  What is the weather in New York?
- What is the time in New York?
- What is the weather in Paris?
- What is the time in Paris?

```shell
[user]: what is the weather in New York?
[weather_time_agent]: OK. The weather in New York is sunny with a temperature of 25 degrees Celsius (77 degrees Fahrenheit).

[user]: What is the time in New York?
[weather_time_agent]: OK. The current time in New York is 2025-11-01 15:42:59 EDT-0400.

[user]: What is the weather in Paris?
[weather_time_agent]: Sorry, weather information for Paris is not available.
```

Go back to parent Readme: [click here](../README.md)