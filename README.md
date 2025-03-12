├── .github
    └── ISSUE_TEMPLATE
    │   ├── bug_report.md
    │   ├── feature_request.md
    │   └── question.md
├── README.md
├── docs
    ├── agents.md
    ├── config.md
    ├── context.md
    ├── guardrails.md
    ├── handoffs.md
    ├── index.md
    ├── models.md
    ├── multi_agent.md
    ├── quickstart.md
    ├── ref
    │   ├── agent.md
    │   ├── agent_output.md
    │   ├── exceptions.md
    │   ├── extensions
    │   │   ├── handoff_filters.md
    │   │   └── handoff_prompt.md
    │   ├── function_schema.md
    │   ├── guardrail.md
    │   ├── handoffs.md
    │   ├── index.md
    │   ├── items.md
    │   ├── lifecycle.md
    │   ├── model_settings.md
    │   ├── models
    │   │   ├── interface.md
    │   │   ├── openai_chatcompletions.md
    │   │   └── openai_responses.md
    │   ├── result.md
    │   ├── run.md
    │   ├── run_context.md
    │   ├── stream_events.md
    │   ├── tool.md
    │   ├── tracing
    │   │   ├── create.md
    │   │   ├── index.md
    │   │   ├── processor_interface.md
    │   │   ├── processors.md
    │   │   ├── scope.md
    │   │   ├── setup.md
    │   │   ├── span_data.md
    │   │   ├── spans.md
    │   │   ├── traces.md
    │   │   └── util.md
    │   └── usage.md
    ├── results.md
    ├── running_agents.md
    ├── streaming.md
    ├── tools.md
    └── tracing.md
└── examples
    ├── agent_patterns
        └── README.md
    └── research_bot
        ├── README.md
        └── sample_outputs
            ├── product_recs.md
            └── vacation.md


/.github/ISSUE_TEMPLATE/bug_report.md:
--------------------------------------------------------------------------------
 1 | ---
 2 | name: Bug report
 3 | about: Report a bug
 4 | title: ''
 5 | labels: bug
 6 | assignees: ''
 7 | 
 8 | ---
 9 | 
10 | ### Please read this first
11 | 
12 | - **Have you read the docs?**[Agents SDK docs](https://openai.github.io/openai-agents-python/)
13 | - **Have you searched for related issues?** Others may have faced similar issues.
14 | 
15 | ### Describe the bug
16 | A clear and concise description of what the bug is.
17 | 
18 | ### Debug information
19 | - Agents SDK version: (e.g. `v0.0.3`)
20 | - Python version (e.g. Python 3.10)
21 | 
22 | ### Repro steps
23 | 
24 | Ideally provide a minimal python script that can be run to reproduce the bug.
25 | 
26 | 
27 | ### Expected behavior
28 | A clear and concise description of what you expected to happen.
29 | 


--------------------------------------------------------------------------------
/.github/ISSUE_TEMPLATE/feature_request.md:
--------------------------------------------------------------------------------
 1 | ---
 2 | name: Feature request
 3 | about: Suggest an idea for this project
 4 | title: ''
 5 | labels: enhancement
 6 | assignees: ''
 7 | 
 8 | ---
 9 | 
10 | ### Please read this first
11 | 
12 | - **Have you read the docs?**[Agents SDK docs](https://openai.github.io/openai-agents-python/)
13 | - **Have you searched for related issues?** Others may have had similar requesrs
14 | 
15 | ### Describe the feature
16 | What is the feature you're requesting? How would it work? Please provide examples and details if possible.
17 | 


--------------------------------------------------------------------------------
/.github/ISSUE_TEMPLATE/question.md:
--------------------------------------------------------------------------------
 1 | ---
 2 | name: Question
 3 | about: Questions about the SDK
 4 | title: ''
 5 | labels: question
 6 | assignees: ''
 7 | 
 8 | ---
 9 | 
10 | ### Please read this first
11 | 
12 | - **Have you read the docs?**[Agents SDK docs](https://openai.github.io/openai-agents-python/)
13 | - **Have you searched for related issues?** Others may have had similar requesrs
14 | 
15 | ### Question
16 | Describe your question. Provide details if available.
17 | 


--------------------------------------------------------------------------------
/README.md:
--------------------------------------------------------------------------------
  1 | # OpenAI Agents SDK
  2 | 
  3 | The OpenAI Agents SDK is a lightweight yet powerful framework for building multi-agent workflows.
  4 | 
  5 | <img src="https://cdn.openai.com/API/docs/images/orchestration.png" alt="Image of the Agents Tracing UI" style="max-height: 803px;">
  6 | 
  7 | ### Core concepts:
  8 | 
  9 | 1. [**Agents**](https://openai.github.io/openai-agents-python/agents): LLMs configured with instructions, tools, guardrails, and handoffs
 10 | 2. [**Handoffs**](https://openai.github.io/openai-agents-python/handoffs/): Allow agents to transfer control to other agents for specific tasks
 11 | 3. [**Guardrails**](https://openai.github.io/openai-agents-python/guardrails/): Configurable safety checks for input and output validation
 12 | 4. [**Tracing**](https://openai.github.io/openai-agents-python/tracing/): Built-in tracking of agent runs, allowing you to view, debug and optimize your workflows
 13 | 
 14 | Explore the [examples](examples) directory to see the SDK in action, and read our [documentation](https://openai.github.io/openai-agents-python/) for more details.
 15 | 
 16 | Notably, our SDK [is compatible](https://openai.github.io/openai-agents-python/models/) with any model providers that support the OpenAI Chat Completions API format.
 17 | 
 18 | ## Get started
 19 | 
 20 | 1. Set up your Python environment
 21 | 
 22 | ```
 23 | python -m venv env
 24 | source env/bin/activate
 25 | ```
 26 | 
 27 | 2. Install Agents SDK
 28 | 
 29 | ```
 30 | pip install openai-agents
 31 | ```
 32 | 
 33 | ## Hello world example
 34 | 
 35 | ```python
 36 | from agents import Agent, Runner
 37 | 
 38 | agent = Agent(name="Assistant", instructions="You are a helpful assistant")
 39 | 
 40 | result = Runner.run_sync(agent, "Write a haiku about recursion in programming.")
 41 | print(result.final_output)
 42 | 
 43 | # Code within the code,
 44 | # Functions calling themselves,
 45 | # Infinite loop's dance.
 46 | ```
 47 | 
 48 | (_If running this, ensure you set the `OPENAI_API_KEY` environment variable_)
 49 | 
 50 | ## Handoffs example
 51 | 
 52 | ```py
 53 | from agents import Agent, Runner
 54 | import asyncio
 55 | 
 56 | spanish_agent = Agent(
 57 |     name="Spanish agent",
 58 |     instructions="You only speak Spanish.",
 59 | )
 60 | 
 61 | english_agent = Agent(
 62 |     name="English agent",
 63 |     instructions="You only speak English",
 64 | )
 65 | 
 66 | triage_agent = Agent(
 67 |     name="Triage agent",
 68 |     instructions="Handoff to the appropriate agent based on the language of the request.",
 69 |     handoffs=[spanish_agent, english_agent],
 70 | )
 71 | 
 72 | 
 73 | async def main():
 74 |     result = await Runner.run(triage_agent, input="Hola, ¿cómo estás?")
 75 |     print(result.final_output)
 76 |     # ¡Hola! Estoy bien, gracias por preguntar. ¿Y tú, cómo estás?
 77 | 
 78 | 
 79 | if __name__ == "__main__":
 80 |     asyncio.run(main())
 81 | ```
 82 | 
 83 | ## Functions example
 84 | 
 85 | ```python
 86 | import asyncio
 87 | 
 88 | from agents import Agent, Runner, function_tool
 89 | 
 90 | 
 91 | @function_tool
 92 | def get_weather(city: str) -> str:
 93 |     return f"The weather in {city} is sunny."
 94 | 
 95 | 
 96 | agent = Agent(
 97 |     name="Hello world",
 98 |     instructions="You are a helpful agent.",
 99 |     tools=[get_weather],
100 | )
101 | 
102 | 
103 | async def main():
104 |     result = await Runner.run(agent, input="What's the weather in Tokyo?")
105 |     print(result.final_output)
106 |     # The weather in Tokyo is sunny.
107 | 
108 | 
109 | if __name__ == "__main__":
110 |     asyncio.run(main())
111 | ```
112 | 
113 | ## The agent loop
114 | 
115 | When you call `Runner.run()`, we run a loop until we get a final output.
116 | 
117 | 1. We call the LLM, using the model and settings on the agent, and the message history.
118 | 2. The LLM returns a response, which may include tool calls.
119 | 3. If the response has a final output (see below for more on this), we return it and end the loop.
120 | 4. If the response has a handoff, we set the agent to the new agent and go back to step 1.
121 | 5. We process the tool calls (if any) and append the tool responses messages. Then we go to step 1.
122 | 
123 | There is a `max_turns` parameter that you can use to limit the number of times the loop executes.
124 | 
125 | ### Final output
126 | 
127 | Final output is the last thing the agent produces in the loop.
128 | 
129 | 1.  If you set an `output_type` on the agent, the final output is when the LLM returns something of that type. We use [structured outputs](https://platform.openai.com/docs/guides/structured-outputs) for this.
130 | 2.  If there's no `output_type` (i.e. plain text responses), then the first LLM response without any tool calls or handoffs is considered as the final output.
131 | 
132 | As a result, the mental model for the agent loop is:
133 | 
134 | 1. If the current agent has an `output_type`, the loop runs until the agent produces structured output matching that type.
135 | 2. If the current agent does not have an `output_type`, the loop runs until the current agent produces a message without any tool calls/handoffs.
136 | 
137 | ## Common agent patterns
138 | 
139 | The Agents SDK is designed to be highly flexible, allowing you to model a wide range of LLM workflows including deterministic flows, iterative loops, and more. See examples in [`examples/agent_patterns`](examples/agent_patterns).
140 | 
141 | ## Tracing
142 | 
143 | The Agents SDK automatically traces your agent runs, making it easy to track and debug the behavior of your agents. Tracing is extensible by design, supporting custom spans and a wide variety of external destinations, including [Logfire](https://logfire.pydantic.dev/docs/integrations/llms/openai/#openai-agents), [AgentOps](https://docs.agentops.ai/v1/integrations/agentssdk), and [Braintrust](https://braintrust.dev/docs/guides/traces/integrations#openai-agents-sdk). For more details about how to customize or disable tracing, see [Tracing](http://openai.github.io/openai-agents-python/tracing).
144 | 
145 | ## Development (only needed if you need to edit the SDK/examples)
146 | 
147 | 0. Ensure you have [`uv`](https://docs.astral.sh/uv/) installed.
148 | 
149 | ```bash
150 | uv --version
151 | ```
152 | 
153 | 1. Install dependencies
154 | 
155 | ```bash
156 | make sync
157 | ```
158 | 
159 | 2. (After making changes) lint/test
160 | 
161 | ```
162 | make tests  # run tests
163 | make mypy   # run typechecker
164 | make lint   # run linter
165 | ```
166 | 
167 | ## Acknowledgements
168 | 
169 | We'd like to acknowledge the excellent work of the open-source community, especially:
170 | 
171 | -   [Pydantic](https://docs.pydantic.dev/latest/) (data validation) and [PydanticAI](https://ai.pydantic.dev/) (advanced agent framework)
172 | -   [MkDocs](https://github.com/squidfunk/mkdocs-material)
173 | -   [Griffe](https://github.com/mkdocstrings/griffe)
174 | -   [uv](https://github.com/astral-sh/uv) and [ruff](https://github.com/astral-sh/ruff)
175 | 
176 | We're committed to continuing to build the Agents SDK as an open source framework so others in the community can expand on our approach.
177 | 


--------------------------------------------------------------------------------
/docs/agents.md:
--------------------------------------------------------------------------------
  1 | # Agents
  2 | 
  3 | Agents are the core building block in your apps. An agent is a large language model (LLM), configured with instructions and tools.
  4 | 
  5 | ## Basic configuration
  6 | 
  7 | The most common properties of an agent you'll configure are:
  8 | 
  9 | -   `instructions`: also known as a developer message or system prompt.
 10 | -   `model`: which LLM to use, and optional `model_settings` to configure model tuning parameters like temperature, top_p, etc.
 11 | -   `tools`: Tools that the agent can use to achieve its tasks.
 12 | 
 13 | ```python
 14 | from agents import Agent, ModelSettings, function_tool
 15 | 
 16 | def get_weather(city: str) -> str:
 17 |     return f"The weather in {city} is sunny"
 18 | 
 19 | agent = Agent(
 20 |     name="Haiku agent",
 21 |     instructions="Always respond in haiku form",
 22 |     model="o3-mini",
 23 |     tools=[function_tool(get_weather)],
 24 | )
 25 | ```
 26 | 
 27 | ## Context
 28 | 
 29 | Agents are generic on their `context` type. Context is a dependency-injection tool: it's an object you create and pass to `Runner.run()`, that is passed to every agent, tool, handoff etc, and it serves as a grab bag of dependencies and state for the agent run. You can provide any Python object as the context.
 30 | 
 31 | ```python
 32 | @dataclass
 33 | class UserContext:
 34 |   uid: str
 35 |   is_pro_user: bool
 36 | 
 37 |   async def fetch_purchases() -> list[Purchase]:
 38 |      return ...
 39 | 
 40 | agent = Agent[UserContext](
 41 |     ...,
 42 | )
 43 | ```
 44 | 
 45 | ## Output types
 46 | 
 47 | By default, agents produce plain text (i.e. `str`) outputs. If you want the agent to produce a particular type of output, you can use the `output_type` parameter. A common choice is to use [Pydantic](https://docs.pydantic.dev/) objects, but we support any type that can be wrapped in a Pydantic [TypeAdapter](https://docs.pydantic.dev/latest/api/type_adapter/) - dataclasses, lists, TypedDict, etc.
 48 | 
 49 | ```python
 50 | from pydantic import BaseModel
 51 | from agents import Agent
 52 | 
 53 | 
 54 | class CalendarEvent(BaseModel):
 55 |     name: str
 56 |     date: str
 57 |     participants: list[str]
 58 | 
 59 | agent = Agent(
 60 |     name="Calendar extractor",
 61 |     instructions="Extract calendar events from text",
 62 |     output_type=CalendarEvent,
 63 | )
 64 | ```
 65 | 
 66 | !!! note
 67 | 
 68 |     When you pass an `output_type`, that tells the model to use [structured outputs](https://platform.openai.com/docs/guides/structured-outputs) instead of regular plain text responses.
 69 | 
 70 | ## Handoffs
 71 | 
 72 | Handoffs are sub-agents that the agent can delegate to. You provide a list of handoffs, and the agent can choose to delegate to them if relevant. This is a powerful pattern that allows orchestrating modular, specialized agents that excel at a single task. Read more in the [handoffs](handoffs.md) documentation.
 73 | 
 74 | ```python
 75 | from agents import Agent
 76 | 
 77 | booking_agent = Agent(...)
 78 | refund_agent = Agent(...)
 79 | 
 80 | triage_agent = Agent(
 81 |     name="Triage agent",
 82 |     instructions=(
 83 |         "Help the user with their questions."
 84 |         "If they ask about booking, handoff to the booking agent."
 85 |         "If they ask about refunds, handoff to the refund agent."
 86 |     ),
 87 |     handoffs=[booking_agent, refund_agent],
 88 | )
 89 | ```
 90 | 
 91 | ## Dynamic instructions
 92 | 
 93 | In most cases, you can provide instructions when you create the agent. However, you can also provide dynamic instructions via a function. The function will receive the agent and context, and must return the prompt. Both regular and `async` functions are accepted.
 94 | 
 95 | ```python
 96 | def dynamic_instructions(
 97 |     context: RunContextWrapper[UserContext], agent: Agent[UserContext]
 98 | ) -> str:
 99 |     return f"The user's name is {context.context.name}. Help them with their questions."
100 | 
101 | 
102 | agent = Agent[UserContext](
103 |     name="Triage agent",
104 |     instructions=dynamic_instructions,
105 | )
106 | ```
107 | 
108 | ## Lifecycle events (hooks)
109 | 
110 | Sometimes, you want to observe the lifecycle of an agent. For example, you may want to log events, or pre-fetch data when certain events occur. You can hook into the agent lifecycle with the `hooks` property. Subclass the [`AgentHooks`][agents.lifecycle.AgentHooks] class, and override the methods you're interested in.
111 | 
112 | ## Guardrails
113 | 
114 | Guardrails allow you to run checks/validations on user input, in parallel to the agent running. For example, you could screen the user's input for relevance. Read more in the [guardrails](guardrails.md) documentation.
115 | 
116 | ## Cloning/copying agents
117 | 
118 | By using the `clone()` method on an agent, you can duplicate an Agent, and optionally change any properties you like.
119 | 
120 | ```python
121 | pirate_agent = Agent(
122 |     name="Pirate",
123 |     instructions="Write like a pirate",
124 |     model="o3-mini",
125 | )
126 | 
127 | robot_agent = pirate_agent.clone(
128 |     name="Robot",
129 |     instructions="Write like a robot",
130 | )
131 | ```
132 | 


--------------------------------------------------------------------------------
/docs/config.md:
--------------------------------------------------------------------------------
 1 | # Configuring the SDK
 2 | 
 3 | ## API keys and clients
 4 | 
 5 | By default, the SDK looks for the `OPENAI_API_KEY` environment variable for LLM requests and tracing, as soon as it is imported. If you are unable to set that environment variable before your app starts, you can use the [set_default_openai_key()][agents.set_default_openai_key] function to set the key.
 6 | 
 7 | ```python
 8 | from agents import set_default_openai_key
 9 | 
10 | set_default_openai_key("sk-...")
11 | ```
12 | 
13 | Alternatively, you can also configure an OpenAI client to be used. By default, the SDK creates an `AsyncOpenAI` instance, using the API key from the environment variable or the default key set above. You can change this by using the [set_default_openai_client()][agents.set_default_openai_client] function.
14 | 
15 | ```python
16 | from openai import AsyncOpenAI
17 | from agents import set_default_openai_client
18 | 
19 | custom_client = AsyncOpenAI(base_url="...", api_key="...")
20 | set_default_openai_client(custom_client)
21 | ```
22 | 
23 | Finally, you can also customize the OpenAI API that is used. By default, we use the OpenAI Responses API. You can override this to use the Chat Completions API by using the [set_default_openai_api()][agents.set_default_openai_api] function.
24 | 
25 | ```python
26 | from agents import set_default_openai_api
27 | 
28 | set_default_openai_api("chat_completions")
29 | ```
30 | 
31 | ## Tracing
32 | 
33 | Tracing is enabled by default. It uses the OpenAI API keys from the section above by default (i.e. the environment variable or the default key you set). You can specifically set the API key used for tracing by using the [`set_tracing_export_api_key`][agents.set_tracing_export_api_key] function.
34 | 
35 | ```python
36 | from agents import set_tracing_export_api_key
37 | 
38 | set_tracing_export_api_key("sk-...")
39 | ```
40 | 
41 | You can also disable tracing entirely by using the [`set_tracing_disabled()`][agents.set_tracing_disabled] function.
42 | 
43 | ```python
44 | from agents import set_tracing_disabled
45 | 
46 | set_tracing_disabled(True)
47 | ```
48 | 
49 | ## Debug logging
50 | 
51 | The SDK has two Python loggers without any handlers set. By default, this means that warnings and errors are sent to `stdout`, but other logs are suppressed.
52 | 
53 | To enable verbose logging, use the [`enable_verbose_stdout_logging()`][agents.enable_verbose_stdout_logging] function.
54 | 
55 | ```python
56 | from agents import enable_verbose_stdout_logging
57 | 
58 | enable_verbose_stdout_logging()
59 | ```
60 | 
61 | Alternatively, you can customize the logs by adding handlers, filters, formatters, etc. You can read more in the [Python logging guide](https://docs.python.org/3/howto/logging.html).
62 | 
63 | ```python
64 | import logging
65 | 
66 | logger =  logging.getLogger("openai.agents") # or openai.agents.tracing for the Tracing logger
67 | 
68 | # To make all logs show up
69 | logger.setLevel(logging.DEBUG)
70 | # To make info and above show up
71 | logger.setLevel(logging.INFO)
72 | # To make warning and above show up
73 | logger.setLevel(logging.WARNING)
74 | # etc
75 | 
76 | # You can customize this as needed, but this will output to `stderr` by default
77 | logger.addHandler(logging.StreamHandler())
78 | ```
79 | 
80 | ### Sensitive data in logs
81 | 
82 | Certain logs may contain sensitive data (for example, user data). If you want to disable this data from being logged, set the following environment variables.
83 | 
84 | To disable logging LLM inputs and outputs:
85 | 
86 | ```bash
87 | export OPENAI_AGENTS_DONT_LOG_MODEL_DATA=1
88 | ```
89 | 
90 | To disable logging tool inputs and outputs:
91 | 
92 | ```bash
93 | export OPENAI_AGENTS_DONT_LOG_TOOL_DATA=1
94 | ```
95 | 


--------------------------------------------------------------------------------
/docs/context.md:
--------------------------------------------------------------------------------
 1 | # Context management
 2 | 
 3 | Context is an overloaded term. There are two main classes of context you might care about:
 4 | 
 5 | 1. Context available locally to your code: this is data and dependencies you might need when tool functions run, during callbacks like `on_handoff`, in lifecycle hooks, etc.
 6 | 2. Context available to LLMs: this is data the LLM sees when generating a response.
 7 | 
 8 | ## Local context
 9 | 
10 | This is represented via the [`RunContextWrapper`][agents.run_context.RunContextWrapper] class and the [`context`][agents.run_context.RunContextWrapper.context] property within it. The way this works is:
11 | 
12 | 1. You create any Python object you want. A common pattern is to use a dataclass or a Pydantic object.
13 | 2. You pass that object to the various run methods (e.g. `Runner.run(..., **context=whatever**))`.
14 | 3. All your tool calls, lifecycle hooks etc will be passed a wrapper object, `RunContextWrapper[T]`, where `T` represents your context object type which you can access via `wrapper.context`.
15 | 
16 | The **most important** thing to be aware of: every agent, tool function, lifecycle etc for a given agent run must use the same _type_ of context.
17 | 
18 | You can use the context for things like:
19 | 
20 | -   Contextual data for your run (e.g. things like a username/uid or other information about the user)
21 | -   Dependencies (e.g. logger objects, data fetchers, etc)
22 | -   Helper functions
23 | 
24 | !!! danger "Note"
25 | 
26 |     The context object is **not** sent to the LLM. It is purely a local object that you can read from, write to and call methods on it.
27 | 
28 | ```python
29 | import asyncio
30 | from dataclasses import dataclass
31 | 
32 | from agents import Agent, RunContextWrapper, Runner, function_tool
33 | 
34 | @dataclass
35 | class UserInfo:  # (1)!
36 |     name: str
37 |     uid: int
38 | 
39 | async def fetch_user_age(wrapper: RunContextWrapper[UserInfo]) -> str:  # (2)!
40 |     return f"User {wrapper.context.name} is 47 years old"
41 | 
42 | async def main():
43 |     user_info = UserInfo(name="John", uid=123)  # (3)!
44 | 
45 |     agent = Agent[UserInfo](  # (4)!
46 |         name="Assistant",
47 |         tools=[function_tool(fetch_user_age)],
48 |     )
49 | 
50 |     result = await Runner.run(
51 |         starting_agent=agent,
52 |         input="What is the age of the user?",
53 |         context=user_info,
54 |     )
55 | 
56 |     print(result.final_output)  # (5)!
57 |     # The user John is 47 years old.
58 | 
59 | if __name__ == "__main__":
60 |     asyncio.run(main())
61 | ```
62 | 
63 | 1. This is the context object. We've used a dataclass here, but you can use any type.
64 | 2. This is a tool. You can see it takes a `RunContextWrapper[UserInfo]`. The tool implementation reads from the context.
65 | 3. We mark the agent with the generic `UserInfo`, so that the typechecker can catch errors (for example, if we tried to pass a tool that took a different context type).
66 | 4. The context is passed to the `run` function.
67 | 5. The agent correctly calls the tool and gets the age.
68 | 
69 | ## Agent/LLM context
70 | 
71 | When an LLM is called, the **only** data it can see is from the conversation history. This means that if you want to make some new data available to the LLM, you must do it in a way that makes it available in that history. There are a few ways to do this:
72 | 
73 | 1. You can add it to the Agent `instructions`. This is also known as a "system prompt" or "developer message". System prompts can be static strings, or they can be dynamic functions that receive the context and output a string. This is a common tactic for information that is always useful (for example, the user's name or the current date).
74 | 2. Add it to the `input` when calling the `Runner.run` functions. This is similar to the `instructions` tactic, but allows you to have messages that are lower in the [chain of command](https://cdn.openai.com/spec/model-spec-2024-05-08.html#follow-the-chain-of-command).
75 | 3. Expose it via function tools. This is useful for _on-demand_ context - the LLM decides when it needs some data, and can call the tool to fetch that data.
76 | 4. Use retrieval or web search. These are special tools that are able to fetch relevant data from files or databases (retrieval), or from the web (web search). This is useful for "grounding" the response in relevant contextual data.
77 | 


--------------------------------------------------------------------------------
/docs/guardrails.md:
--------------------------------------------------------------------------------
  1 | # Guardrails
  2 | 
  3 | Guardrails run _in parallel_ to your agents, enabling you to do checks and validations of user input. For example, imagine you have an agent that uses a very smart (and hence slow/expensive) model to help with customer requests. You wouldn't want malicious users to ask the model to help them with their math homework. So, you can run a guardrail with a fast/cheap model. If the guardrail detects malicious usage, it can immediately raise an error, which stops the expensive model from running and saves you time/money.
  4 | 
  5 | There are two kinds of guardrails:
  6 | 
  7 | 1. Input guardrails run on the initial user input
  8 | 2. Output guardrails run on the final agent output
  9 | 
 10 | ## Input guardrails
 11 | 
 12 | Input guardrails run in 3 steps:
 13 | 
 14 | 1. First, the guardrail receives the same input passed to the agent.
 15 | 2. Next, the guardrail function runs to produce a [`GuardrailFunctionOutput`][agents.guardrail.GuardrailFunctionOutput], which is then wrapped in an [`InputGuardrailResult`][agents.guardrail.InputGuardrailResult]
 16 | 3. Finally, we check if [`.tripwire_triggered`][agents.guardrail.GuardrailFunctionOutput.tripwire_triggered] is true. If true, an [`InputGuardrailTripwireTriggered`][agents.exceptions.InputGuardrailTripwireTriggered] exception is raised, so you can appropriately respond to the user or handle the exception.
 17 | 
 18 | !!! Note
 19 | 
 20 |     Input guardrails are intended to run on user input, so an agent's guardrails only run if the agent is the *first* agent. You might wonder, why is the `guardrails` property on the agent instead of passed to `Runner.run`? It's because guardrails tend to be related to the actual Agent - you'd run different guardrails for different agents, so colocating the code is useful for readability.
 21 | 
 22 | ## Output guardrails
 23 | 
 24 | Output guardrails run in 3 steps:
 25 | 
 26 | 1. First, the guardrail receives the same input passed to the agent.
 27 | 2. Next, the guardrail function runs to produce a [`GuardrailFunctionOutput`][agents.guardrail.GuardrailFunctionOutput], which is then wrapped in an [`OutputGuardrailResult`][agents.guardrail.OutputGuardrailResult]
 28 | 3. Finally, we check if [`.tripwire_triggered`][agents.guardrail.GuardrailFunctionOutput.tripwire_triggered] is true. If true, an [`OutputGuardrailTripwireTriggered`][agents.exceptions.OutputGuardrailTripwireTriggered] exception is raised, so you can appropriately respond to the user or handle the exception.
 29 | 
 30 | !!! Note
 31 | 
 32 |     Output guardrails are intended to run on the final agent input, so an agent's guardrails only run if the agent is the *last* agent. Similar to the input guardrails, we do this because guardrails tend to be related to the actual Agent - you'd run different guardrails for different agents, so colocating the code is useful for readability.
 33 | 
 34 | ## Tripwires
 35 | 
 36 | If the input or output fails the guardrail, the Guardrail can signal this with a tripwire. As soon as we see a guardrail that has triggered the tripwires, we immediately raise a `{Input,Output}GuardrailTripwireTriggered` exception and halt the Agent execution.
 37 | 
 38 | ## Implementing a guardrail
 39 | 
 40 | You need to provide a function that receives input, and returns a [`GuardrailFunctionOutput`][agents.guardrail.GuardrailFunctionOutput]. In this example, we'll do this by running an Agent under the hood.
 41 | 
 42 | ```python
 43 | from pydantic import BaseModel
 44 | from agents import (
 45 |     Agent,
 46 |     GuardrailFunctionOutput,
 47 |     InputGuardrailTripwireTriggered,
 48 |     RunContextWrapper,
 49 |     Runner,
 50 |     TResponseInputItem,
 51 |     input_guardrail,
 52 | )
 53 | 
 54 | class MathHomeworkOutput(BaseModel):
 55 |     is_math_homework: bool
 56 |     reasoning: str
 57 | 
 58 | guardrail_agent = Agent( # (1)!
 59 |     name="Guardrail check",
 60 |     instructions="Check if the user is asking you to do their math homework.",
 61 |     output_type=MathHomeworkOutput,
 62 | )
 63 | 
 64 | 
 65 | @input_guardrail
 66 | async def math_guardrail( # (2)!
 67 |     ctx: RunContextWrapper[None], agent: Agent, input: str | list[TResponseInputItem]
 68 | ) -> GuardrailFunctionOutput:
 69 |     result = await Runner.run(guardrail_agent, input, context=ctx.context)
 70 | 
 71 |     return GuardrailFunctionOutput(
 72 |         output_info=result.final_output, # (3)!
 73 |         tripwire_triggered=result.final_output.is_math_homework,
 74 |     )
 75 | 
 76 | 
 77 | agent = Agent(  # (4)!
 78 |     name="Customer support agent",
 79 |     instructions="You are a customer support agent. You help customers with their questions.",
 80 |     input_guardrails=[math_guardrail],
 81 | )
 82 | 
 83 | async def main():
 84 |     # This should trip the guardrail
 85 |     try:
 86 |         await Runner.run(agent, "Hello, can you help me solve for x: 2x + 3 = 11?")
 87 |         print("Guardrail didn't trip - this is unexpected")
 88 | 
 89 |     except InputGuardrailTripwireTriggered:
 90 |         print("Math homework guardrail tripped")
 91 | ```
 92 | 
 93 | 1. We'll use this agent in our guardrail function.
 94 | 2. This is the guardrail function that receives the agent's input/context, and returns the result.
 95 | 3. We can include extra information in the guardrail result.
 96 | 4. This is the actual agent that defines the workflow.
 97 | 
 98 | Output guardrails are similar.
 99 | 
100 | ```python
101 | from pydantic import BaseModel
102 | from agents import (
103 |     Agent,
104 |     GuardrailFunctionOutput,
105 |     OutputGuardrailTripwireTriggered,
106 |     RunContextWrapper,
107 |     Runner,
108 |     output_guardrail,
109 | )
110 | class MessageOutput(BaseModel): # (1)!
111 |     response: str
112 | 
113 | class MathOutput(BaseModel): # (2)!
114 |     is_math: bool
115 |     reasoning: str
116 | 
117 | guardrail_agent = Agent(
118 |     name="Guardrail check",
119 |     instructions="Check if the output includes any math.",
120 |     output_type=MathOutput,
121 | )
122 | 
123 | @output_guardrail
124 | async def math_guardrail(  # (3)!
125 |     ctx: RunContextWrapper, agent: Agent, output: MessageOutput
126 | ) -> GuardrailFunctionOutput:
127 |     result = await Runner.run(guardrail_agent, output.response, context=ctx.context)
128 | 
129 |     return GuardrailFunctionOutput(
130 |         output_info=result.final_output,
131 |         tripwire_triggered=result.final_output.is_math,
132 |     )
133 | 
134 | agent = Agent( # (4)!
135 |     name="Customer support agent",
136 |     instructions="You are a customer support agent. You help customers with their questions.",
137 |     output_guardrails=[math_guardrail],
138 |     output_type=MessageOutput,
139 | )
140 | 
141 | async def main():
142 |     # This should trip the guardrail
143 |     try:
144 |         await Runner.run(agent, "Hello, can you help me solve for x: 2x + 3 = 11?")
145 |         print("Guardrail didn't trip - this is unexpected")
146 | 
147 |     except OutputGuardrailTripwireTriggered:
148 |         print("Math output guardrail tripped")
149 | ```
150 | 
151 | 1. This is the actual agent's output type.
152 | 2. This is the guardrail's output type.
153 | 3. This is the guardrail function that receives the agent's output, and returns the result.
154 | 4. This is the actual agent that defines the workflow.
155 | 


--------------------------------------------------------------------------------
/docs/handoffs.md:
--------------------------------------------------------------------------------
  1 | # Handoffs
  2 | 
  3 | Handoffs allow an agent to delegate tasks to another agent. This is particularly useful in scenarios where different agents specialize in distinct areas. For example, a customer support app might have agents that each specifically handle tasks like order status, refunds, FAQs, etc.
  4 | 
  5 | Handoffs are represented as tools to the LLM. So if there's a handoff to an agent named `Refund Agent`, the tool would be called `transfer_to_refund_agent`.
  6 | 
  7 | ## Creating a handoff
  8 | 
  9 | All agents have a [`handoffs`][agents.agent.Agent.handoffs] param, which can either take an `Agent` directly, or a `Handoff` object that customizes the Handoff.
 10 | 
 11 | You can create a handoff using the [`handoff()`][agents.handoffs.handoff] function provided by the Agents SDK. This function allows you to specify the agent to hand off to, along with optional overrides and input filters.
 12 | 
 13 | ### Basic Usage
 14 | 
 15 | Here's how you can create a simple handoff:
 16 | 
 17 | ```python
 18 | from agents import Agent, handoff
 19 | 
 20 | billing_agent = Agent(name="Billing agent")
 21 | refund_agent = Agent(name="Refund agent")
 22 | 
 23 | # (1)!
 24 | triage_agent = Agent(name="Triage agent", handoffs=[billing_agent, handoff(refund_agent)])
 25 | ```
 26 | 
 27 | 1. You can use the agent directly (as in `billing_agent`), or you can use the `handoff()` function.
 28 | 
 29 | ### Customizing handoffs via the `handoff()` function
 30 | 
 31 | The [`handoff()`][agents.handoffs.handoff] function lets you customize things.
 32 | 
 33 | -   `agent`: This is the agent to which things will be handed off.
 34 | -   `tool_name_override`: By default, the `Handoff.default_tool_name()` function is used, which resolves to `transfer_to_<agent_name>`. You can override this.
 35 | -   `tool_description_override`: Override the default tool description from `Handoff.default_tool_description()`
 36 | -   `on_handoff`: A callback function executed when the handoff is invoked. This is useful for things like kicking off some data fetching as soon as you know a handoff is being invoked. This function receives the agent context, and can optionally also receive LLM generated input. The input data is controlled by the `input_type` param.
 37 | -   `input_type`: The type of input expected by the handoff (optional).
 38 | -   `input_filter`: This lets you filter the input received by the next agent. See below for more.
 39 | 
 40 | ```python
 41 | from agents import Agent, handoff, RunContextWrapper
 42 | 
 43 | def on_handoff(ctx: RunContextWrapper[None]):
 44 |     print("Handoff called")
 45 | 
 46 | agent = Agent(name="My agent")
 47 | 
 48 | handoff_obj = handoff(
 49 |     agent=agent,
 50 |     on_handoff=on_handoff,
 51 |     tool_name_override="custom_handoff_tool",
 52 |     tool_description_override="Custom description",
 53 | )
 54 | ```
 55 | 
 56 | ## Handoff inputs
 57 | 
 58 | In certain situations, you want the LLM to provide some data when it calls a handoff. For example, imagine a handoff to an "Escalation agent". You might want a reason to be provided, so you can log it.
 59 | 
 60 | ```python
 61 | from pydantic import BaseModel
 62 | 
 63 | from agents import Agent, handoff, RunContextWrapper
 64 | 
 65 | class EscalationData(BaseModel):
 66 |     reason: str
 67 | 
 68 | async def on_handoff(ctx: RunContextWrapper[None], input_data: EscalationData):
 69 |     print(f"Escalation agent called with reason: {input_data.reason}")
 70 | 
 71 | agent = Agent(name="Escalation agent")
 72 | 
 73 | handoff_obj = handoff(
 74 |     agent=agent,
 75 |     on_handoff=on_handoff,
 76 |     input_type=EscalationData,
 77 | )
 78 | ```
 79 | 
 80 | ## Input filters
 81 | 
 82 | When a handoff occurs, it's as though the new agent takes over the conversation, and gets to see the entire previous conversation history. If you want to change this, you can set an [`input_filter`][agents.handoffs.Handoff.input_filter]. An input filter is a function that receives the existing input via a [`HandoffInputData`][agents.handoffs.HandoffInputData], and must return a new `HandoffInputData`.
 83 | 
 84 | There are some common patterns (for example removing all tool calls from the history), which are implemented for you in [`agents.extensions.handoff_filters`][]
 85 | 
 86 | ```python
 87 | from agents import Agent, handoff
 88 | from agents.extensions import handoff_filters
 89 | 
 90 | agent = Agent(name="FAQ agent")
 91 | 
 92 | handoff_obj = handoff(
 93 |     agent=agent,
 94 |     input_filter=handoff_filters.remove_all_tools, # (1)!
 95 | )
 96 | ```
 97 | 
 98 | 1. This will automatically remove all tools from the history when `FAQ agent` is called.
 99 | 
100 | ## Recommended prompts
101 | 
102 | To make sure that LLMs understand handoffs properly, we recommend including information about handoffs in your agents. We have a suggested prefix in [`agents.extensions.handoff_prompt.RECOMMENDED_PROMPT_PREFIX`][], or you can call [`agents.extensions.handoff_prompt.prompt_with_handoff_instructions`][] to automatically add recommended data to your prompts.
103 | 
104 | ```python
105 | from agents import Agent
106 | from agents.extensions.handoff_prompt import RECOMMENDED_PROMPT_PREFIX
107 | 
108 | billing_agent = Agent(
109 |     name="Billing agent",
110 |     instructions=f"""{RECOMMENDED_PROMPT_PREFIX}
111 |     <Fill in the rest of your prompt here>.""",
112 | )
113 | ```
114 | 


--------------------------------------------------------------------------------
/docs/index.md:
--------------------------------------------------------------------------------
 1 | # OpenAI Agents SDK
 2 | 
 3 | The [OpenAI Agents SDK](https://github.com/openai/openai-agents-python) enables you to build agentic AI apps in a lightweight, easy-to-use package with very few abstractions. It's a production-ready upgrade of our previous experimentation for agents, [Swarm](https://github.com/openai/swarm/tree/main). The Agents SDK has a very small set of primitives:
 4 | 
 5 | -   **Agents**, which are LLMs equipped with instructions and tools
 6 | -   **Handoffs**, which allow agents to delegate to other agents for specific tasks
 7 | -   **Guardrails**, which enable the inputs to agents to be validated
 8 | 
 9 | In combination with Python, these primitives are powerful enough to express complex relationships between tools and agents, and allow you to build real-world applications without a steep learning curve. In addition, the SDK comes with built-in **tracing** that lets you visualize and debug your agentic flows, as well as evaluate them and even fine-tune models for your application.
10 | 
11 | ## Why use the Agents SDK
12 | 
13 | The SDK has two driving design principles:
14 | 
15 | 1. Enough features to be worth using, but few enough primitives to make it quick to learn.
16 | 2. Works great out of the box, but you can customize exactly what happens.
17 | 
18 | Here are the main features of the SDK:
19 | 
20 | -   Agent loop: Built-in agent loop that handles calling tools, sending results to the LLM, and looping until the LLM is done.
21 | -   Python-first: Use built-in language features to orchestrate and chain agents, rather than needing to learn new abstractions.
22 | -   Handoffs: A powerful feature to coordinate and delegate between multiple agents.
23 | -   Guardrails: Run input validations and checks in parallel to your agents, breaking early if the checks fail.
24 | -   Function tools: Turn any Python function into a tool, with automatic schema generation and Pydantic-powered validation.
25 | -   Tracing: Built-in tracing that lets you visualize, debug and monitor your workflows, as well as use the OpenAI suite of evaluation, fine-tuning and distillation tools.
26 | 
27 | ## Installation
28 | 
29 | ```bash
30 | pip install openai-agents
31 | ```
32 | 
33 | ## Hello world example
34 | 
35 | ```python
36 | from agents import Agent, Runner
37 | 
38 | agent = Agent(name="Assistant", instructions="You are a helpful assistant")
39 | 
40 | result = Runner.run_sync(agent, "Write a haiku about recursion in programming.")
41 | print(result.final_output)
42 | 
43 | # Code within the code,
44 | # Functions calling themselves,
45 | # Infinite loop's dance.
46 | ```
47 | 
48 | (_If running this, ensure you set the `OPENAI_API_KEY` environment variable_)
49 | 
50 | ```bash
51 | export OPENAI_API_KEY=sk-...
52 | ```
53 | 


--------------------------------------------------------------------------------
/docs/models.md:
--------------------------------------------------------------------------------
 1 | # Models
 2 | 
 3 | The Agents SDK comes with out-of-the-box support for OpenAI models in two flavors:
 4 | 
 5 | -   **Recommended**: the [`OpenAIResponsesModel`][agents.models.openai_responses.OpenAIResponsesModel], which calls OpenAI APIs using the new [Responses API](https://platform.openai.com/docs/api-reference/responses).
 6 | -   The [`OpenAIChatCompletionsModel`][agents.models.openai_chatcompletions.OpenAIChatCompletionsModel], which calls OpenAI APIs using the [Chat Completions API](https://platform.openai.com/docs/api-reference/chat).
 7 | 
 8 | ## Mixing and matching models
 9 | 
10 | Within a single workflow, you may want to use different models for each agent. For example, you could use a smaller, faster model for triage, while using a larger, more capable model for complex tasks. When configuring an [`Agent`][agents.Agent], you can select a specific model by either:
11 | 
12 | 1. Passing the name of an OpenAI model.
13 | 2. Passing any model name + a [`ModelProvider`][agents.models.interface.ModelProvider] that can map that name to a Model instance.
14 | 3. Directly providing a [`Model`][agents.models.interface.Model] implementation.
15 | 
16 | !!!note
17 | 
18 |     While our SDK supports both the [`OpenAIResponsesModel`][agents.models.openai_responses.OpenAIResponsesModel] and the [`OpenAIChatCompletionsModel`][agents.models.openai_chatcompletions.OpenAIChatCompletionsModel] shapes, we recommend using a single model shape for each workflow because the two shapes support a different set of features and tools. If your workflow requires mixing and matching model shapes, make sure that all the features you're using are available on both.
19 | 
20 | ```python
21 | from agents import Agent, Runner, AsyncOpenAI, OpenAIChatCompletionsModel
22 | import asyncio
23 | 
24 | spanish_agent = Agent(
25 |     name="Spanish agent",
26 |     instructions="You only speak Spanish.",
27 |     model="o3-mini", # (1)!
28 | )
29 | 
30 | english_agent = Agent(
31 |     name="English agent",
32 |     instructions="You only speak English",
33 |     model=OpenAIChatCompletionsModel( # (2)!
34 |         model="gpt-4o",
35 |         openai_client=AsyncOpenAI()
36 |     ),
37 | )
38 | 
39 | triage_agent = Agent(
40 |     name="Triage agent",
41 |     instructions="Handoff to the appropriate agent based on the language of the request.",
42 |     handoffs=[spanish_agent, english_agent],
43 |     model="gpt-3.5-turbo",
44 | )
45 | 
46 | async def main():
47 |     result = await Runner.run(triage_agent, input="Hola, ¿cómo estás?")
48 |     print(result.final_output)
49 | ```
50 | 
51 | 1.  Sets the name of an OpenAI model directly.
52 | 2.  Provides a [`Model`][agents.models.interface.Model] implementation.
53 | 
54 | ## Using other LLM providers
55 | 
56 | Many providers also support the OpenAI API format, which means you can pass a `base_url` to the existing OpenAI model implementations and use them easily. `ModelSettings` is used to configure tuning parameters (e.g., temperature, top_p) for the model you select.
57 | 
58 | ```python
59 | external_client = AsyncOpenAI(
60 |     api_key="EXTERNAL_API_KEY",
61 |     base_url="https://api.external.com/v1/",
62 | )
63 | 
64 | spanish_agent = Agent(
65 |     name="Spanish agent",
66 |     instructions="You only speak Spanish.",
67 |     model=OpenAIChatCompletionsModel(
68 |         model="EXTERNAL_MODEL_NAME",
69 |         openai_client=external_client,
70 |     ),
71 |     model_settings=ModelSettings(temperature=0.5),
72 | )
73 | ```
74 | 


--------------------------------------------------------------------------------
/docs/multi_agent.md:
--------------------------------------------------------------------------------
 1 | # Orchestrating multiple agents
 2 | 
 3 | Orchestration refers to the flow of agents in your app. Which agents run, in what order, and how do they decide what happens next? There are two main ways to orchestrate agents:
 4 | 
 5 | 1. Allowing the LLM to make decisions: this uses the intelligence of an LLM to plan, reason, and decide on what steps to take based on that.
 6 | 2. Orchestrating via code: determining the flow of agents via your code.
 7 | 
 8 | You can mix and match these patterns. Each has their own tradeoffs, described below.
 9 | 
10 | ## Orchestrating via LLM
11 | 
12 | An agent is an LLM equipped with instructions, tools and handoffs. This means that given an open-ended task, the LLM can autonomously plan how it will tackle the task, using tools to take actions and acquire data, and using handoffs to delegate tasks to sub-agents. For example, a research agent could be equipped with tools like:
13 | 
14 | -   Web search to find information online
15 | -   File search and retrieval to search through proprietary data and connections
16 | -   Computer use to take actions on a computer
17 | -   Code execution to do data analysis
18 | -   Handoffs to specialized agents that are great at planning, report writing and more.
19 | 
20 | This pattern is great when the task is open-ended and you want to rely on the intelligence of an LLM. The most important tactics here are:
21 | 
22 | 1. Invest in good prompts. Make it clear what tools are available, how to use them, and what parameters it must operate within.
23 | 2. Monitor your app and iterate on it. See where things go wrong, and iterate on your prompts.
24 | 3. Allow the agent to introspect and improve. For example, run it in a loop, and let it critique itself; or, provide error messages and let it improve.
25 | 4. Have specialized agents that excel in one task, rather than having a general purpose agent that is expected to be good at anything.
26 | 5. Invest in [evals](https://platform.openai.com/docs/guides/evals). This lets you train your agents to improve and get better at tasks.
27 | 
28 | ## Orchestrating via code
29 | 
30 | While orchestrating via LLM is powerful, orchestrating via code makes tasks more deterministic and predictable, in terms of speed, cost and performance. Common patterns here are:
31 | 
32 | -   Using [structured outputs](https://platform.openai.com/docs/guides/structured-outputs) to generate well formed data that you can inspect with your code. For example, you might ask an agent to classify the task into a few categories, and then pick the next agent based on the category.
33 | -   Chaining multiple agents by transforming the output of one into the input of the next. You can decompose a task like writing a blog post into a series of steps - do research, write an outline, write the blog post, critique it, and then improve it.
34 | -   Running the agent that performs the task in a `while` loop with an agent that evaluates and provides feedback, until the evaluator says the output passes certain criteria.
35 | -   Running multiple agents in parallel, e.g. via Python primitives like `asyncio.gather`. This is useful for speed when you have multiple tasks that don't depend on each other.
36 | 
37 | We have a number of examples in [`examples/agent_patterns`](https://github.com/openai/openai-agents-python/tree/main/examples/agent_patterns).
38 | 


--------------------------------------------------------------------------------
/docs/quickstart.md:
--------------------------------------------------------------------------------
  1 | # Quickstart
  2 | 
  3 | ## Create a project and virtual environment
  4 | 
  5 | You'll only need to do this once.
  6 | 
  7 | ```bash
  8 | mkdir my_project
  9 | cd my_project
 10 | python -m venv .venv
 11 | ```
 12 | 
 13 | ### Activate the virtual environment
 14 | 
 15 | Do this every time you start a new terminal session.
 16 | 
 17 | ```bash
 18 | source .venv/bin/activate
 19 | ```
 20 | 
 21 | ### Install the Agents SDK
 22 | 
 23 | ```bash
 24 | pip install openai-agents # or `uv add openai-agents`, etc
 25 | ```
 26 | 
 27 | ### Set an OpenAI API key
 28 | 
 29 | If you don't have one, follow [these instructions](https://platform.openai.com/docs/quickstart#create-and-export-an-api-key) to create an OpenAI API key.
 30 | 
 31 | ```bash
 32 | export OPENAI_API_KEY=sk-...
 33 | ```
 34 | 
 35 | ## Create your first agent
 36 | 
 37 | Agents are defined with instructions, a name, and optional config (such as `model_config`)
 38 | 
 39 | ```python
 40 | from agents import Agent
 41 | 
 42 | agent = Agent(
 43 |     name="Math Tutor",
 44 |     instructions="You provide help with math problems. Explain your reasoning at each step and include examples",
 45 | )
 46 | ```
 47 | 
 48 | ## Add a few more agents
 49 | 
 50 | Additional agents can be defined in the same way. `handoff_descriptions` provide additional context for determining handoff routing
 51 | 
 52 | ```python
 53 | from agents import Agent
 54 | 
 55 | history_tutor_agent = Agent(
 56 |     name="History Tutor",
 57 |     handoff_description="Specialist agent for historical questions",
 58 |     instructions="You provide assistance with historical queries. Explain important events and context clearly.",
 59 | )
 60 | 
 61 | math_tutor_agent = Agent(
 62 |     name="Math Tutor",
 63 |     handoff_description="Specialist agent for math questions",
 64 |     instructions="You provide help with math problems. Explain your reasoning at each step and include examples",
 65 | )
 66 | ```
 67 | 
 68 | ## Define your handoffs
 69 | 
 70 | On each agent, you can define an inventory of outgoing handoff options that the agent can choose from to decide how to make progress on their task.
 71 | 
 72 | ```python
 73 | triage_agent = Agent(
 74 |     name="Triage Agent",
 75 |     instructions="You determine which agent to use based on the user's homework question",
 76 |     handoffs=[history_tutor_agent, math_tutor_agent]
 77 | )
 78 | ```
 79 | 
 80 | ## Run the agent orchestration
 81 | 
 82 | Let's check that the workflow runs and the triage agent correctly routes between the two specialist agents.
 83 | 
 84 | ```python
 85 | from agents import Runner
 86 | 
 87 | async def main():
 88 |     result = await Runner.run(triage_agent, "What is the capital of France?")
 89 |     print(result.final_output)
 90 | ```
 91 | 
 92 | ## Add a guardrail
 93 | 
 94 | You can define custom guardrails to run on the input or output.
 95 | 
 96 | ```python
 97 | from agents import GuardrailFunctionOutput, Agent, Runner
 98 | from pydantic import BaseModel
 99 | 
100 | class HomeworkOutput(BaseModel):
101 |     is_homework: bool
102 |     reasoning: str
103 | 
104 | guardrail_agent = Agent(
105 |     name="Guardrail check",
106 |     instructions="Check if the user is asking about homework.",
107 |     output_type=HomeworkOutput,
108 | )
109 | 
110 | async def homework_guardrail(ctx, agent, input_data):
111 |     result = await Runner.run(guardrail_agent, input_data, context=ctx.context)
112 |     final_output = result.final_output_as(HomeworkOutput)
113 |     return GuardrailFunctionOutput(
114 |         output_info=final_output,
115 |         tripwire_triggered=not final_output.is_homework,
116 |     )
117 | ```
118 | 
119 | ## Put it all together
120 | 
121 | Let's put it all together and run the entire workflow, using handoffs and the input guardrail.
122 | 
123 | ```python
124 | from agents import Agent, InputGuardrail,GuardrailFunctionOutput, Runner
125 | from pydantic import BaseModel
126 | import asyncio
127 | 
128 | class HomeworkOutput(BaseModel):
129 |     is_homework: bool
130 |     reasoning: str
131 | 
132 | guardrail_agent = Agent(
133 |     name="Guardrail check",
134 |     instructions="Check if the user is asking about homework.",
135 |     output_type=HomeworkOutput,
136 | )
137 | 
138 | math_tutor_agent = Agent(
139 |     name="Math Tutor",
140 |     handoff_description="Specialist agent for math questions",
141 |     instructions="You provide help with math problems. Explain your reasoning at each step and include examples",
142 | )
143 | 
144 | history_tutor_agent = Agent(
145 |     name="History Tutor",
146 |     handoff_description="Specialist agent for historical questions",
147 |     instructions="You provide assistance with historical queries. Explain important events and context clearly.",
148 | )
149 | 
150 | 
151 | async def homework_guardrail(ctx, agent, input_data):
152 |     result = await Runner.run(guardrail_agent, input_data, context=ctx.context)
153 |     final_output = result.final_output_as(HomeworkOutput)
154 |     return GuardrailFunctionOutput(
155 |         output_info=final_output,
156 |         tripwire_triggered=not final_output.is_homework,
157 |     )
158 | 
159 | triage_agent = Agent(
160 |     name="Triage Agent",
161 |     instructions="You determine which agent to use based on the user's homework question",
162 |     handoffs=[history_tutor_agent, math_tutor_agent],
163 |     input_guardrails=[
164 |         InputGuardrail(guardrail_function=homework_guardrail),
165 |     ],
166 | )
167 | 
168 | async def main():
169 |     result = await Runner.run(triage_agent, "who was the first president of the united states?")
170 |     print(result.final_output)
171 | 
172 |     result = await Runner.run(triage_agent, "what is life")
173 |     print(result.final_output)
174 | 
175 | if __name__ == "__main__":
176 |     asyncio.run(main())
177 | ```
178 | 
179 | ## View your traces
180 | 
181 | To review what happened during your agent run, navigate to the [Trace viewer in the OpenAI Dashboard](https://platform.openai.com/traces) to view traces of your agent runs.
182 | 
183 | ## Next steps
184 | 
185 | Learn how to build more complex agentic flows:
186 | 
187 | -   Learn about how to configure [Agents](agents.md).
188 | -   Learn about [running agents](running_agents.md).
189 | -   Learn about [tools](tools.md), [guardrails](guardrails.md) and [models](models.md).
190 | 


--------------------------------------------------------------------------------
/docs/ref/agent.md:
--------------------------------------------------------------------------------
1 | # `Agents`
2 | 
3 | ::: agents.agent
4 | 


--------------------------------------------------------------------------------
/docs/ref/agent_output.md:
--------------------------------------------------------------------------------
1 | # `Agent output`
2 | 
3 | ::: agents.agent_output
4 | 


--------------------------------------------------------------------------------
/docs/ref/exceptions.md:
--------------------------------------------------------------------------------
1 | # `Exceptions`
2 | 
3 | ::: agents.exceptions
4 | 


--------------------------------------------------------------------------------
/docs/ref/extensions/handoff_filters.md:
--------------------------------------------------------------------------------
1 | # `Handoff filters`
2 | 
3 | ::: agents.extensions.handoff_filters
4 | 


--------------------------------------------------------------------------------
/docs/ref/extensions/handoff_prompt.md:
--------------------------------------------------------------------------------
1 | # `Handoff prompt`
2 | 
3 | ::: agents.extensions.handoff_prompt
4 | 
5 |     options:
6 |         members:
7 |             - RECOMMENDED_PROMPT_PREFIX
8 |             - prompt_with_handoff_instructions
9 | 


--------------------------------------------------------------------------------
/docs/ref/function_schema.md:
--------------------------------------------------------------------------------
1 | # `Function schema`
2 | 
3 | ::: agents.function_schema
4 | 


--------------------------------------------------------------------------------
/docs/ref/guardrail.md:
--------------------------------------------------------------------------------
1 | # `Guardrails`
2 | 
3 | ::: agents.guardrail
4 | 


--------------------------------------------------------------------------------
/docs/ref/handoffs.md:
--------------------------------------------------------------------------------
1 | # `Handoffs`
2 | 
3 | ::: agents.handoffs
4 | 


--------------------------------------------------------------------------------
/docs/ref/index.md:
--------------------------------------------------------------------------------
 1 | # Agents module
 2 | 
 3 | ::: agents
 4 | 
 5 |     options:
 6 |         members:
 7 |             - set_default_openai_key
 8 |             - set_default_openai_client
 9 |             - set_default_openai_api
10 |             - set_tracing_export_api_key
11 |             - set_tracing_disabled
12 |             - set_trace_processors
13 |             - enable_verbose_stdout_logging
14 | 


--------------------------------------------------------------------------------
/docs/ref/items.md:
--------------------------------------------------------------------------------
1 | # `Items`
2 | 
3 | ::: agents.items
4 | 


--------------------------------------------------------------------------------
/docs/ref/lifecycle.md:
--------------------------------------------------------------------------------
1 | # `Lifecycle`
2 | 
3 | ::: agents.lifecycle
4 | 
5 |     options:
6 |         show_source: false
7 | 


--------------------------------------------------------------------------------
/docs/ref/model_settings.md:
--------------------------------------------------------------------------------
1 | # `Model settings`
2 | 
3 | ::: agents.model_settings
4 | 


--------------------------------------------------------------------------------
/docs/ref/models/interface.md:
--------------------------------------------------------------------------------
1 | # `Model interface`
2 | 
3 | ::: agents.models.interface
4 | 


--------------------------------------------------------------------------------
/docs/ref/models/openai_chatcompletions.md:
--------------------------------------------------------------------------------
1 | # `OpenAI Chat Completions model`
2 | 
3 | ::: agents.models.openai_chatcompletions
4 | 


--------------------------------------------------------------------------------
/docs/ref/models/openai_responses.md:
--------------------------------------------------------------------------------
1 | # `OpenAI Responses model`
2 | 
3 | ::: agents.models.openai_responses
4 | 


--------------------------------------------------------------------------------
/docs/ref/result.md:
--------------------------------------------------------------------------------
1 | # `Results`
2 | 
3 | ::: agents.result
4 | 


--------------------------------------------------------------------------------
/docs/ref/run.md:
--------------------------------------------------------------------------------
1 | # `Runner`
2 | 
3 | ::: agents.run
4 | 
5 |     options:
6 |         members:
7 |             - Runner
8 |             - RunConfig
9 | 


--------------------------------------------------------------------------------
/docs/ref/run_context.md:
--------------------------------------------------------------------------------
1 | # `Run context`
2 | 
3 | ::: agents.run_context
4 | 


--------------------------------------------------------------------------------
/docs/ref/stream_events.md:
--------------------------------------------------------------------------------
1 | # `Streaming events`
2 | 
3 | ::: agents.stream_events
4 | 


--------------------------------------------------------------------------------
/docs/ref/tool.md:
--------------------------------------------------------------------------------
1 | # `Tools`
2 | 
3 | ::: agents.tool
4 | 


--------------------------------------------------------------------------------
/docs/ref/tracing/create.md:
--------------------------------------------------------------------------------
1 | # `Creating traces/spans`
2 | 
3 | ::: agents.tracing.create
4 | 


--------------------------------------------------------------------------------
/docs/ref/tracing/index.md:
--------------------------------------------------------------------------------
1 | # Tracing module
2 | 
3 | ::: agents.tracing
4 | 


--------------------------------------------------------------------------------
/docs/ref/tracing/processor_interface.md:
--------------------------------------------------------------------------------
1 | # `Processor interface`
2 | 
3 | ::: agents.tracing.processor_interface
4 | 


--------------------------------------------------------------------------------
/docs/ref/tracing/processors.md:
--------------------------------------------------------------------------------
1 | # `Processors`
2 | 
3 | ::: agents.tracing.processors
4 | 


--------------------------------------------------------------------------------
/docs/ref/tracing/scope.md:
--------------------------------------------------------------------------------
1 | # `Scope`
2 | 
3 | ::: agents.tracing.scope
4 | 


--------------------------------------------------------------------------------
/docs/ref/tracing/setup.md:
--------------------------------------------------------------------------------
1 | # `Setup`
2 | 
3 | ::: agents.tracing.setup
4 | 


--------------------------------------------------------------------------------
/docs/ref/tracing/span_data.md:
--------------------------------------------------------------------------------
1 | # `Span data`
2 | 
3 | ::: agents.tracing.span_data
4 | 


--------------------------------------------------------------------------------
/docs/ref/tracing/spans.md:
--------------------------------------------------------------------------------
 1 | # `Spans`
 2 | 
 3 | ::: agents.tracing.spans
 4 | 
 5 |     options:
 6 |         members:
 7 |             - Span
 8 |             - NoOpSpan
 9 |             - SpanImpl
10 | 


--------------------------------------------------------------------------------
/docs/ref/tracing/traces.md:
--------------------------------------------------------------------------------
1 | # `Traces`
2 | 
3 | ::: agents.tracing.traces
4 | 


--------------------------------------------------------------------------------
/docs/ref/tracing/util.md:
--------------------------------------------------------------------------------
1 | # `Util`
2 | 
3 | ::: agents.tracing.util
4 | 


--------------------------------------------------------------------------------
/docs/ref/usage.md:
--------------------------------------------------------------------------------
1 | # `Usage`
2 | 
3 | ::: agents.usage
4 | 


--------------------------------------------------------------------------------
/docs/results.md:
--------------------------------------------------------------------------------
 1 | # Results
 2 | 
 3 | When you call the `Runner.run` methods, you either get a:
 4 | 
 5 | -   [`RunResult`][agents.result.RunResult] if you call `run` or `run_sync`
 6 | -   [`RunResultStreaming`][agents.result.RunResultStreaming] if you call `run_streamed`
 7 | 
 8 | Both of these inherit from [`RunResultBase`][agents.result.RunResultBase], which is where most useful information is present.
 9 | 
10 | ## Final output
11 | 
12 | The [`final_output`][agents.result.RunResultBase.final_output] property contains the final output of the last agent that ran. This is either:
13 | 
14 | -   a `str`, if the last agent didn't have an `output_type` defined
15 | -   an object of type `last_agent.output_type`, if the agent had an output type defined.
16 | 
17 | !!! note
18 | 
19 |     `final_output` is of type `Any`. We can't statically type this, because of handoffs. If handoffs occur, that means any Agent might be the last agent, so we don't statically know the set of possible output types.
20 | 
21 | ## Inputs for the next turn
22 | 
23 | You can use [`result.to_input_list()`][agents.result.RunResultBase.to_input_list] to turn the result into an input list that concatenates the original input you provided, to the items generated during the agent run. This makes it convenient to take the outputs of one agent run and pass them into another run, or to run it in a loop and append new user inputs each time.
24 | 
25 | ## Last agent
26 | 
27 | The [`last_agent`][agents.result.RunResultBase.last_agent] property contains the last agent that ran. Depending on your application, this is often useful for the next time the user inputs something. For example, if you have a frontline triage agent that hands off to a language-specific agent, you can store the last agent, and re-use it the next time the user messages the agent.
28 | 
29 | ## New items
30 | 
31 | The [`new_items`][agents.result.RunResultBase.new_items] property contains the new items generated during the run. The items are [`RunItem`][agents.items.RunItem]s. A run item wraps the raw item generated by the LLM.
32 | 
33 | -   [`MessageOutputItem`][agents.items.MessageOutputItem] indicates a message from the LLM. The raw item is the message generated.
34 | -   [`HandoffCallItem`][agents.items.HandoffCallItem] indicates that the LLM called the handoff tool. The raw item is the tool call item from the LLM.
35 | -   [`HandoffOutputItem`][agents.items.HandoffOutputItem] indicates that a handoff occurred. The raw item is the tool response to the handoff tool call. You can also access the source/target agents from the item.
36 | -   [`ToolCallItem`][agents.items.ToolCallItem] indicates that the LLM invoked a tool.
37 | -   [`ToolCallOutputItem`][agents.items.ToolCallOutputItem] indicates that a tool was called. The raw item is the tool response. You can also access the tool output from the item.
38 | -   [`ReasoningItem`][agents.items.ReasoningItem] indicates a reasoning item from the LLM. The raw item is the reasoning generated.
39 | 
40 | ## Other information
41 | 
42 | ### Guardrail results
43 | 
44 | The [`input_guardrail_results`][agents.result.RunResultBase.input_guardrail_results] and [`output_guardrail_results`][agents.result.RunResultBase.output_guardrail_results] properties contain the results of the guardrails, if any. Guardrail results can sometimes contain useful information you want to log or store, so we make these available to you.
45 | 
46 | ### Raw responses
47 | 
48 | The [`raw_responses`][agents.result.RunResultBase.raw_responses] property contains the [`ModelResponse`][agents.items.ModelResponse]s generated by the LLM.
49 | 
50 | ### Original input
51 | 
52 | The [`input`][agents.result.RunResultBase.input] property contains the original input you provided to the `run` method. In most cases you won't need this, but it's available in case you do.
53 | 


--------------------------------------------------------------------------------
/docs/running_agents.md:
--------------------------------------------------------------------------------
 1 | # Running agents
 2 | 
 3 | You can run agents via the [`Runner`][agents.run.Runner] class. You have 3 options:
 4 | 
 5 | 1. [`Runner.run()`][agents.run.Runner.run], which runs async and returns a [`RunResult`][agents.result.RunResult].
 6 | 2. [`Runner.run_sync()`][agents.run.Runner.run_sync], which is a sync method and just runs `.run()` under the hood.
 7 | 3. [`Runner.run_streamed()`][agents.run.Runner.run_streamed], which runs async and returns a [`RunResultStreaming`][agents.result.RunResultStreaming]. It calls the LLM in streaming mode, and streams those events to you as they are received.
 8 | 
 9 | ```python
10 | from agents import Agent, Runner
11 | 
12 | async def main():
13 |     agent = Agent(name="Assistant", instructions="You are a helpful assistant")
14 | 
15 |     result = await Runner.run(agent, "Write a haiku about recursion in programming.")
16 |     print(result.final_output)
17 |     # Code within the code,
18 |     # Functions calling themselves,
19 |     # Infinite loop's dance.
20 | ```
21 | 
22 | Read more in the [results guide](results.md).
23 | 
24 | ## The agent loop
25 | 
26 | When you use the run method in `Runner`, you pass in a starting agent and input. The input can either be a string (which is considered a user message), or a list of input items, which are the items in the OpenAI Responses API.
27 | 
28 | The runner then runs a loop:
29 | 
30 | 1. We call the LLM for the current agent, with the current input.
31 | 2. The LLM produces its output.
32 |     1. If the LLM returns a `final_output`, the loop ends and we return the result.
33 |     2. If the LLM does a handoff, we update the current agent and input, and re-run the loop.
34 |     3. If the LLM produces tool calls, we run those tool calls, append the results, and re-run the loop.
35 | 3. If we exceed the `max_turns` passed, we raise a [`MaxTurnsExceeded`][agents.exceptions.MaxTurnsExceeded] exception.
36 | 
37 | !!! note
38 | 
39 |     The rule for whether the LLM output is considered as a "final output" is that it produces text output with the desired type, and there are no tool calls.
40 | 
41 | ## Streaming
42 | 
43 | Streaming allows you to additionally receive streaming events as the LLM runs. Once the stream is done, the [`RunResultStreaming`][agents.result.RunResultStreaming] will contain the complete information about the run, including all the new outputs produces. You can call `.stream_events()` for the streaming events. Read more in the [streaming guide](streaming.md).
44 | 
45 | ## Run config
46 | 
47 | The `run_config` parameter lets you configure some global settings for the agent run:
48 | 
49 | -   [`model`][agents.run.RunConfig.model]: Allows setting a global LLM model to use, irrespective of what `model` each Agent has.
50 | -   [`model_provider`][agents.run.RunConfig.model_provider]: A model provider for looking up model names, which defaults to OpenAI.
51 | -   [`model_settings`][agents.run.RunConfig.model_settings]: Overrides agent-specific settings. For example, you can set a global `temperature` or `top_p`.
52 | -   [`input_guardrails`][agents.run.RunConfig.input_guardrails], [`output_guardrails`][agents.run.RunConfig.output_guardrails]: A list of input or output guardrails to include on all runs.
53 | -   [`handoff_input_filter`][agents.run.RunConfig.handoff_input_filter]: A global input filter to apply to all handoffs, if the handoff doesn't already have one. The input filter allows you to edit the inputs that are sent to the new agent. See the documentation in [`Handoff.input_filter`][agents.handoffs.Handoff.input_filter] for more details.
54 | -   [`tracing_disabled`][agents.run.RunConfig.tracing_disabled]: Allows you to disable [tracing](tracing.md) for the entire run.
55 | -   [`trace_include_sensitive_data`][agents.run.RunConfig.trace_include_sensitive_data]: Configures whether traces will include potentially sensitive data, such as LLM and tool call inputs/outputs.
56 | -   [`workflow_name`][agents.run.RunConfig.workflow_name], [`trace_id`][agents.run.RunConfig.trace_id], [`group_id`][agents.run.RunConfig.group_id]: Sets the tracing workflow name, trace ID and trace group ID for the run. We recommend at least setting `workflow_name`. The session ID is an optional field that lets you link traces across multiple runs.
57 | -   [`trace_metadata`][agents.run.RunConfig.trace_metadata]: Metadata to include on all traces.
58 | 
59 | ## Conversations/chat threads
60 | 
61 | Calling any of the run methods can result in one or more agents running (and hence one or more LLM calls), but it represents a single logical turn in a chat conversation. For example:
62 | 
63 | 1. User turn: user enter text
64 | 2. Runner run: first agent calls LLM, runs tools, does a handoff to a second agent, second agent runs more tools, and then produces an output.
65 | 
66 | At the end of the agent run, you can choose what to show to the user. For example, you might show the user every new item generated by the agents, or just the final output. Either way, the user might then ask a followup question, in which case you can call the run method again.
67 | 
68 | You can use the base [`RunResultBase.to_input_list()`][agents.result.RunResultBase.to_input_list] method to get the inputs for the next turn.
69 | 
70 | ```python
71 | async def main():
72 |     agent = Agent(name="Assistant", instructions="Reply very concisely.")
73 | 
74 |     with trace(workflow_name="Conversation", group_id=thread_id):
75 |         # First turn
76 |         result = await Runner.run(agent, "What city is the Golden Gate Bridge in?")
77 |         print(result.final_output)
78 |         # San Francisco
79 | 
80 |         # Second turn
81 |         new_input = output.to_input_list() + [{"role": "user", "content": "What state is it in?"}]
82 |         result = await Runner.run(agent, new_input)
83 |         print(result.final_output)
84 |         # California
85 | ```
86 | 
87 | ## Exceptions
88 | 
89 | The SDK raises exceptions in certain cases. The full list is in [`agents.exceptions`][]. As an overview:
90 | 
91 | -   [`AgentsException`][agents.exceptions.AgentsException] is the base class for all exceptions raised in the SDK.
92 | -   [`MaxTurnsExceeded`][agents.exceptions.MaxTurnsExceeded] is raised when the run exceeds the `max_turns` passed to the run methods.
93 | -   [`ModelBehaviorError`][agents.exceptions.ModelBehaviorError] is raised when the model produces invalid outputs, e.g. malformed JSON or using non-existent tools.
94 | -   [`UserError`][agents.exceptions.UserError] is raised when you (the person writing code using the SDK) make an error using the SDK.
95 | -   [`InputGuardrailTripwireTriggered`][agents.exceptions.InputGuardrailTripwireTriggered], [`OutputGuardrailTripwireTriggered`][agents.exceptions.OutputGuardrailTripwireTriggered] is raised when a [guardrail](guardrails.md) is tripped.
96 | 


--------------------------------------------------------------------------------
/docs/streaming.md:
--------------------------------------------------------------------------------
 1 | # Streaming
 2 | 
 3 | Streaming lets you subscribe to updates of the agent run as it proceeds. This can be useful for showing the end-user progress updates and partial responses.
 4 | 
 5 | To stream, you can call [`Runner.run_streamed()`][agents.run.Runner.run_streamed], which will give you a [`RunResultStreaming`][agents.result.RunResultStreaming]. Calling `result.stream_events()` gives you an async stream of [`StreamEvent`][agents.stream_events.StreamEvent] objects, which are described below.
 6 | 
 7 | ## Raw response events
 8 | 
 9 | [`RawResponsesStreamEvent`][agents.stream_events.RawResponsesStreamEvent] are raw events passed directly from the LLM. They are in OpenAI Responses API format, which means each event has a type (like `response.created`, `response.output_text.delta`, etc) and data. These events are useful if you want to stream response messages to the user as soon as they are generated.
10 | 
11 | For example, this will output the text generated by the LLM token-by-token.
12 | 
13 | ```python
14 | import asyncio
15 | from openai.types.responses import ResponseTextDeltaEvent
16 | from agents import Agent, Runner
17 | 
18 | async def main():
19 |     agent = Agent(
20 |         name="Joker",
21 |         instructions="You are a helpful assistant.",
22 |     )
23 | 
24 |     result = Runner.run_streamed(agent, input="Please tell me 5 jokes.")
25 |     async for event in result.stream_events():
26 |         if event.type == "raw_response_event" and isinstance(event.data, ResponseTextDeltaEvent):
27 |             print(event.data.delta, end="", flush=True)
28 | 
29 | 
30 | if __name__ == "__main__":
31 |     asyncio.run(main())
32 | ```
33 | 
34 | ## Run item events and agent events
35 | 
36 | [`RunItemStreamEvent`][agents.stream_events.RunItemStreamEvent]s are higher level events. They inform you when an item has been fully generated. This allows you to push progress updates at the level of "message generated", "tool ran", etc, instead of each token. Similarly, [`AgentUpdatedStreamEvent`][agents.stream_events.AgentUpdatedStreamEvent] gives you updates when the current agent changes (e.g. as the result of a handoff).
37 | 
38 | For example, this will ignore raw events and stream updates to the user.
39 | 
40 | ```python
41 | import asyncio
42 | import random
43 | from agents import Agent, ItemHelpers, Runner, function_tool
44 | 
45 | @function_tool
46 | def how_many_jokes() -> int:
47 |     return random.randint(1, 10)
48 | 
49 | 
50 | async def main():
51 |     agent = Agent(
52 |         name="Joker",
53 |         instructions="First call the `how_many_jokes` tool, then tell that many jokes.",
54 |         tools=[how_many_jokes],
55 |     )
56 | 
57 |     result = Runner.run_streamed(
58 |         agent,
59 |         input="Hello",
60 |     )
61 |     print("=== Run starting ===")
62 | 
63 |     async for event in result.stream_events():
64 |         # We'll ignore the raw responses event deltas
65 |         if event.type == "raw_response_event":
66 |             continue
67 |         # When the agent updates, print that
68 |         elif event.type == "agent_updated_stream_event":
69 |             print(f"Agent updated: {event.new_agent.name}")
70 |             continue
71 |         # When items are generated, print them
72 |         elif event.type == "run_item_stream_event":
73 |             if event.item.type == "tool_call_item":
74 |                 print("-- Tool was called")
75 |             elif event.item.type == "tool_call_output_item":
76 |                 print(f"-- Tool output: {event.item.output}")
77 |             elif event.item.type == "message_output_item":
78 |                 print(f"-- Message output:\n {ItemHelpers.text_message_output(event.item)}")
79 |             else:
80 |                 pass  # Ignore other event types
81 | 
82 |     print("=== Run complete ===")
83 | 
84 | 
85 | if __name__ == "__main__":
86 |     asyncio.run(main())
87 | ```
88 | 


--------------------------------------------------------------------------------
/docs/tools.md:
--------------------------------------------------------------------------------
  1 | # Tools
  2 | 
  3 | Tools let agents take actions: things like fetching data, running code, calling external APIs, and even using a computer. There are three classes of tools in the Agent SDK:
  4 | 
  5 | -   Hosted tools: these run on LLM servers alongside the AI models. OpenAI offers retrieval, web search and computer use as hosted tools.
  6 | -   Function calling: these allow you to use any Python function as a tool.
  7 | -   Agents as tools: this allows you to use an agent as a tool, allowing Agents to call other agents without handing off to them.
  8 | 
  9 | ## Hosted tools
 10 | 
 11 | OpenAI offers a few built-in tools when using the [`OpenAIResponsesModel`][agents.models.openai_responses.OpenAIResponsesModel]:
 12 | 
 13 | -   The [`WebSearchTool`][agents.tool.WebSearchTool] lets an agent search the web.
 14 | -   The [`FileSearchTool`][agents.tool.FileSearchTool] allows retrieving information from your OpenAI Vector Stores.
 15 | -   The [`ComputerTool`][agents.tool.ComputerTool] allows automating computer use tasks.
 16 | 
 17 | ```python
 18 | from agents import Agent, FileSearchTool, Runner, WebSearchTool
 19 | 
 20 | agent = Agent(
 21 |     name="Assistant",
 22 |     tools=[
 23 |         WebSearchTool(),
 24 |         FileSearchTool(
 25 |             max_num_results=3,
 26 |             vector_store_ids=["VECTOR_STORE_ID"],
 27 |         ),
 28 |     ],
 29 | )
 30 | 
 31 | async def main():
 32 |     result = await Runner.run(agent, "Which coffee shop should I go to, taking into account my preferences and the weather today in SF?")
 33 |     print(result.final_output)
 34 | ```
 35 | 
 36 | ## Function tools
 37 | 
 38 | You can use any Python function as a tool. The Agents SDK will setup the tool automatically:
 39 | 
 40 | -   The name of the tool will be the name of the Python function (or you can provide a name)
 41 | -   Tool description will be taken from the docstring of the function (or you can provide a description)
 42 | -   The schema for the function inputs is automatically created from the function's arguments
 43 | -   Descriptions for each input are taken from the docstring of the function, unless disabled
 44 | 
 45 | We use Python's `inspect` module to extract the function signature, along with [`griffe`](https://mkdocstrings.github.io/griffe/) to parse docstrings and `pydantic` for schema creation.
 46 | 
 47 | ```python
 48 | import json
 49 | 
 50 | from typing_extensions import TypedDict, Any
 51 | 
 52 | from agents import Agent, FunctionTool, RunContextWrapper, function_tool
 53 | 
 54 | 
 55 | class Location(TypedDict):
 56 |     lat: float
 57 |     long: float
 58 | 
 59 | @function_tool  # (1)!
 60 | async def fetch_weather(location: Location) -> str:
 61 |     # (2)!
 62 |     """Fetch the weather for a given location.
 63 | 
 64 |     Args:
 65 |         location: The location to fetch the weather for.
 66 |     """
 67 |     # In real life, we'd fetch the weather from a weather API
 68 |     return "sunny"
 69 | 
 70 | 
 71 | @function_tool(name_override="fetch_data")  # (3)!
 72 | def read_file(ctx: RunContextWrapper[Any], path: str, directory: str | None = None) -> str:
 73 |     """Read the contents of a file.
 74 | 
 75 |     Args:
 76 |         path: The path to the file to read.
 77 |         directory: The directory to read the file from.
 78 |     """
 79 |     # In real life, we'd read the file from the file system
 80 |     return "<file contents>"
 81 | 
 82 | 
 83 | agent = Agent(
 84 |     name="Assistant",
 85 |     tools=[fetch_weather, read_file],  # (4)!
 86 | )
 87 | 
 88 | for tool in agent.tools:
 89 |     if isinstance(tool, FunctionTool):
 90 |         print(tool.name)
 91 |         print(tool.description)
 92 |         print(json.dumps(tool.params_json_schema, indent=2))
 93 |         print()
 94 | 
 95 | ```
 96 | 
 97 | 1.  You can use any Python types as arguments to your functions, and the function can be sync or async.
 98 | 2.  Docstrings, if present, are used to capture descriptions and argument descriptions
 99 | 3.  Functions can optionally take the `context` (must be the first argument). You can also set overrides, like the name of the tool, description, which docstring style to use, etc.
100 | 4.  You can pass the decorated functions to the list of tools.
101 | 
102 | ??? note "Expand to see output"
103 | 
104 |     ```
105 |     fetch_weather
106 |     Fetch the weather for a given location.
107 |     {
108 |     "$defs": {
109 |       "Location": {
110 |         "properties": {
111 |           "lat": {
112 |             "title": "Lat",
113 |             "type": "number"
114 |           },
115 |           "long": {
116 |             "title": "Long",
117 |             "type": "number"
118 |           }
119 |         },
120 |         "required": [
121 |           "lat",
122 |           "long"
123 |         ],
124 |         "title": "Location",
125 |         "type": "object"
126 |       }
127 |     },
128 |     "properties": {
129 |       "location": {
130 |         "$ref": "#/$defs/Location",
131 |         "description": "The location to fetch the weather for."
132 |       }
133 |     },
134 |     "required": [
135 |       "location"
136 |     ],
137 |     "title": "fetch_weather_args",
138 |     "type": "object"
139 |     }
140 | 
141 |     fetch_data
142 |     Read the contents of a file.
143 |     {
144 |     "properties": {
145 |       "path": {
146 |         "description": "The path to the file to read.",
147 |         "title": "Path",
148 |         "type": "string"
149 |       },
150 |       "directory": {
151 |         "anyOf": [
152 |           {
153 |             "type": "string"
154 |           },
155 |           {
156 |             "type": "null"
157 |           }
158 |         ],
159 |         "default": null,
160 |         "description": "The directory to read the file from.",
161 |         "title": "Directory"
162 |       }
163 |     },
164 |     "required": [
165 |       "path"
166 |     ],
167 |     "title": "fetch_data_args",
168 |     "type": "object"
169 |     }
170 |     ```
171 | 
172 | ### Custom function tools
173 | 
174 | Sometimes, you don't want to use a Python function as a tool. You can directly create a [`FunctionTool`][agents.tool.FunctionTool] if you prefer. You'll need to provide:
175 | 
176 | -   `name`
177 | -   `description`
178 | -   `params_json_schema`, which is the JSON schema for the arguments
179 | -   `on_invoke_tool`, which is an async function that receives the context and the arguments as a JSON string, and must return the tool output as a string.
180 | 
181 | ```python
182 | from typing import Any
183 | 
184 | from pydantic import BaseModel
185 | 
186 | from agents import RunContextWrapper, FunctionTool
187 | 
188 | 
189 | 
190 | def do_some_work(data: str) -> str:
191 |     return "done"
192 | 
193 | 
194 | class FunctionArgs(BaseModel):
195 |     username: str
196 |     age: int
197 | 
198 | 
199 | async def run_function(ctx: RunContextWrapper[Any], args: str) -> str:
200 |     parsed = FunctionArgs.model_validate_json(args)
201 |     return do_some_work(data=f"{parsed.username} is {parsed.age} years old")
202 | 
203 | 
204 | tool = FunctionTool(
205 |     name="process_user",
206 |     description="Processes extracted user data",
207 |     params_json_schema=FunctionArgs.model_json_schema(),
208 |     on_invoke_tool=run_function,
209 | )
210 | ```
211 | 
212 | ### Automatic argument and docstring parsing
213 | 
214 | As mentioned before, we automatically parse the function signature to extract the schema for the tool, and we parse the docstring to extract descriptions for the tool and for individual arguments. Some notes on that:
215 | 
216 | 1. The signature parsing is done via the `inspect` module. We use type annotations to understand the types for the arguments, and dynamically build a Pydantic model to represent the overall schema. It supports most types, including Python primitives, Pydantic models, TypedDicts, and more.
217 | 2. We use `griffe` to parse docstrings. Supported docstring formats are `google`, `sphinx` and `numpy`. We attempt to automatically detect the docstring format, but this is best-effort and you can explicitly set it when calling `function_tool`. You can also disable docstring parsing by setting `use_docstring_info` to `False`.
218 | 
219 | The code for the schema extraction lives in [`agents.function_schema`][].
220 | 
221 | ## Agents as tools
222 | 
223 | In some workflows, you may want a central agent to orchestrate a network of specialized agents, instead of handing off control. You can do this by modeling agents as tools.
224 | 
225 | ```python
226 | from agents import Agent, Runner
227 | import asyncio
228 | 
229 | spanish_agent = Agent(
230 |     name="Spanish agent",
231 |     instructions="You translate the user's message to Spanish",
232 | )
233 | 
234 | french_agent = Agent(
235 |     name="French agent",
236 |     instructions="You translate the user's message to French",
237 | )
238 | 
239 | orchestrator_agent = Agent(
240 |     name="orchestrator_agent",
241 |     instructions=(
242 |         "You are a translation agent. You use the tools given to you to translate."
243 |         "If asked for multiple translations, you call the relevant tools."
244 |     ),
245 |     tools=[
246 |         spanish_agent.as_tool(
247 |             tool_name="translate_to_spanish",
248 |             tool_description="Translate the user's message to Spanish",
249 |         ),
250 |         french_agent.as_tool(
251 |             tool_name="translate_to_french",
252 |             tool_description="Translate the user's message to French",
253 |         ),
254 |     ],
255 | )
256 | 
257 | async def main():
258 |     result = await Runner.run(orchestrator_agent, input="Say 'Hello, how are you?' in Spanish.")
259 |     print(result.final_output)
260 | ```
261 | 
262 | ## Handling errors in function tools
263 | 
264 | When you create a function tool via `@function_tool`, you can pass a `failure_error_function`. This is a function that provides an error response to the LLM in case the tool call crashes.
265 | 
266 | -   By default (i.e. if you don't pass anything), it runs a `default_tool_error_function` which tells the LLM an error occurred.
267 | -   If you pass your own error function, it runs that instead, and sends the response to the LLM.
268 | -   If you explicitly pass `None`, then any tool call errors will be re-raised for you to handle. This could be a `ModelBehaviorError` if the model produced invalid JSON, or a `UserError` if your code crashed, etc.
269 | 
270 | If you are manually creating a `FunctionTool` object, then you must handle errors inside the `on_invoke_tool` function.
271 | 


--------------------------------------------------------------------------------
/docs/tracing.md:
--------------------------------------------------------------------------------
 1 | # Tracing
 2 | 
 3 | The Agents SDK includes built-in tracing, collecting a comprehensive record of events during an agent run: LLM generations, tool calls, handoffs, guardrails, and even custom events that occur. Using the [Traces dashboard](https://platform.openai.com/traces), you can debug, visualize, and monitor your workflows during development and in production.
 4 | 
 5 | !!!note
 6 | 
 7 |     Tracing is enabled by default. There are two ways to disable tracing:
 8 | 
 9 |     1. You can globally disable tracing by setting the env var `OPENAI_AGENTS_DISABLE_TRACING=1`
10 |     2. You can disable tracing for a single run by setting [`agents.run.RunConfig.tracing_disabled`][] to `True`
11 | 
12 | ## Traces and spans
13 | 
14 | -   **Traces** represent a single end-to-end operation of a "workflow". They're composed of Spans. Traces have the following properties:
15 |     -   `workflow_name`: This is the logical workflow or app. For example "Code generation" or "Customer service".
16 |     -   `trace_id`: A unique ID for the trace. Automatically generated if you don't pass one. Must have the format `trace_<32_alphanumeric>`.
17 |     -   `group_id`: Optional group ID, to link multiple traces from the same conversation. For example, you might use a chat thread ID.
18 |     -   `disabled`: If True, the trace will not be recorded.
19 |     -   `metadata`: Optional metadata for the trace.
20 | -   **Spans** represent operations that have a start and end time. Spans have:
21 |     -   `started_at` and `ended_at` timestamps.
22 |     -   `trace_id`, to represent the trace they belong to
23 |     -   `parent_id`, which points to the parent Span of this Span (if any)
24 |     -   `span_data`, which is information about the Span. For example, `AgentSpanData` contains information about the Agent, `GenerationSpanData` contains information about the LLM generation, etc.
25 | 
26 | ## Default tracing
27 | 
28 | By default, the SDK traces the following:
29 | 
30 | -   The entire `Runner.{run, run_sync, run_streamed}()` is wrapped in a `trace()`.
31 | -   Each time an agent runs, it is wrapped in `agent_span()`
32 | -   LLM generations are wrapped in `generation_span()`
33 | -   Function tool calls are each wrapped in `function_span()`
34 | -   Guardrails are wrapped in `guardrail_span()`
35 | -   Handoffs are wrapped in `handoff_span()`
36 | 
37 | By default, the trace is named "Agent trace". You can set this name if you use `trace`, or you can can configure the name and other properties with the [`RunConfig`][agents.run.RunConfig].
38 | 
39 | In addition, you can set up [custom trace processors](#custom-tracing-processors) to push traces to other destinations (as a replacement, or secondary destination).
40 | 
41 | ## Higher level traces
42 | 
43 | Sometimes, you might want multiple calls to `run()` to be part of a single trace. You can do this by wrapping the entire code in a `trace()`.
44 | 
45 | ```python
46 | from agents import Agent, Runner, trace
47 | 
48 | async def main():
49 |     agent = Agent(name="Joke generator", instructions="Tell funny jokes.")
50 | 
51 |     with trace("Joke workflow"): # (1)!
52 |         first_result = await Runner.run(agent, "Tell me a joke")
53 |         second_result = await Runner.run(agent, f"Rate this joke: {first_output.final_output}")
54 |         print(f"Joke: {first_result.final_output}")
55 |         print(f"Rating: {second_result.final_output}")
56 | ```
57 | 
58 | 1. Because the two calls to `Runner.run` are wrapped in a `with trace()`, the individual runs will be part of the overall trace rather than creating two traces.
59 | 
60 | ## Creating traces
61 | 
62 | You can use the [`trace()`][agents.tracing.trace] function to create a trace. Traces need to be started and finished. You have two options to do so:
63 | 
64 | 1. **Recommended**: use the trace as a context manager, i.e. `with trace(...) as my_trace`. This will automatically start and end the trace at the right time.
65 | 2. You can also manually call [`trace.start()`][agents.tracing.Trace.start] and [`trace.finish()`][agents.tracing.Trace.finish].
66 | 
67 | The current trace is tracked via a Python [`contextvar`](https://docs.python.org/3/library/contextvars.html). This means that it works with concurrency automatically. If you manually start/end a trace, you'll need to pass `mark_as_current` and `reset_current` to `start()`/`finish()` to update the current trace.
68 | 
69 | ## Creating spans
70 | 
71 | You can use the various [`*_span()`][agents.tracing.create] methods to create a span. In general, you don't need to manually create spans. A [`custom_span()`][agents.tracing.custom_span] function is available for tracking custom span information.
72 | 
73 | Spans are automatically part of the current trace, and are nested under the nearest current span, which is tracked via a Python [`contextvar`](https://docs.python.org/3/library/contextvars.html).
74 | 
75 | ## Sensitive data
76 | 
77 | Some spans track potentially sensitive data. For example, the `generation_span()` stores the inputs/outputs of the LLM generation, and `function_span()` stores the inputs/outputs of function calls. These may contain sensitive data, so you can disable capturing that data via [`RunConfig.trace_include_sensitive_data`][agents.run.RunConfig.trace_include_sensitive_data].
78 | 
79 | ## Custom tracing processors
80 | 
81 | The high level architecture for tracing is:
82 | 
83 | -   At initialization, we create a global [`TraceProvider`][agents.tracing.setup.TraceProvider], which is responsible for creating traces.
84 | -   We configure the `TraceProvider` with a [`BatchTraceProcessor`][agents.tracing.processors.BatchTraceProcessor] that sends traces/spans in batches to a [`BackendSpanExporter`][agents.tracing.processors.BackendSpanExporter], which exports the spans and traces to the OpenAI backend in batches.
85 | 
86 | To customize this default setup, to send traces to alternative or additional backends or modifying exporter behavior, you have two options:
87 | 
88 | 1. [`add_trace_processor()`][agents.tracing.add_trace_processor] lets you add an **additional** trace processor that will receive traces and spans as they are ready. This lets you do your own processing in addition to sending traces to OpenAI's backend.
89 | 2. [`set_trace_processors()`][agents.tracing.set_trace_processors] lets you **replace** the default processors with your own trace processors. This means traces will not be sent to the OpenAI backend unless you include a `TracingProcessor` that does so.
90 | 
91 | External trace processors include:
92 | 
93 | -   [Braintrust](https://braintrust.dev/docs/guides/traces/integrations#openai-agents-sdk)
94 | -   [Pydantic Logfire](https://logfire.pydantic.dev/docs/integrations/llms/openai/#openai-agents)
95 | -   [AgentOps](https://docs.agentops.ai/v1/integrations/agentssdk)
96 | 


--------------------------------------------------------------------------------
/examples/agent_patterns/README.md:
--------------------------------------------------------------------------------
 1 | # Common agentic patterns
 2 | 
 3 | This folder contains examples of different common patterns for agents.
 4 | 
 5 | ## Deterministic flows
 6 | 
 7 | A common tactic is to break down a task into a series of smaller steps. Each task can be performed by an agent, and the output of one agent is used as input to the next. For example, if your task was to generate a story, you could break it down into the following steps:
 8 | 
 9 | 1. Generate an outline
10 | 2. Generate the story
11 | 3. Generate the ending
12 | 
13 | Each of these steps can be performed by an agent. The output of one agent is used as input to the next.
14 | 
15 | See the [`deterministic.py`](./deterministic.py) file for an example of this.
16 | 
17 | ## Handoffs and routing
18 | 
19 | In many situations, you have specialized sub-agents that handle specific tasks. You can use handoffs to route the task to the right agent.
20 | 
21 | For example, you might have a frontline agent that receives a request, and then hands off to a specialized agent based on the language of the request.
22 | See the [`routing.py`](./routing.py) file for an example of this.
23 | 
24 | ## Agents as tools
25 | 
26 | The mental model for handoffs is that the new agent "takes over". It sees the previous conversation history, and owns the conversation from that point onwards. However, this is not the only way to use agents. You can also use agents as a tool - the tool agent goes off and runs on its own, and then returns the result to the original agent.
27 | 
28 | For example, you could model the translation task above as tool calls instead: rather than handing over to the language-specific agent, you could call the agent as a tool, and then use the result in the next step. This enables things like translating multiple languages at once.
29 | 
30 | See the [`agents_as_tools.py`](./agents_as_tools.py) file for an example of this.
31 | 
32 | ## LLM-as-a-judge
33 | 
34 | LLMs can often improve the quality of their output if given feedback. A common pattern is to generate a response using a model, and then use a second model to provide feedback. You can even use a small model for the initial generation and a larger model for the feedback, to optimize cost.
35 | 
36 | For example, you could use an LLM to generate an outline for a story, and then use a second LLM to evaluate the outline and provide feedback. You can then use the feedback to improve the outline, and repeat until the LLM is satisfied with the outline.
37 | 
38 | See the [`llm_as_a_judge.py`](./llm_as_a_judge.py) file for an example of this.
39 | 
40 | ## Parallelization
41 | 
42 | Running multiple agents in parallel is a common pattern. This can be useful for both latency (e.g. if you have multiple steps that don't depend on each other) and also for other reasons e.g. generating multiple responses and picking the best one.
43 | 
44 | See the [`parallelization.py`](./parallelization.py) file for an example of this. It runs a translation agent multiple times in parallel, and then picks the best translation.
45 | 
46 | ## Guardrails
47 | 
48 | Related to parallelization, you often want to run input guardrails to make sure the inputs to your agents are valid. For example, if you have a customer support agent, you might want to make sure that the user isn't trying to ask for help with a math problem.
49 | 
50 | You can definitely do this without any special Agents SDK features by using parallelization, but we support a special guardrail primitive. Guardrails can have a "tripwire" - if the tripwire is triggered, the agent execution will immediately stop and a `GuardrailTripwireTriggered` exception will be raised.
51 | 
52 | This is really useful for latency: for example, you might have a very fast model that runs the guardrail and a slow model that runs the actual agent. You wouldn't want to wait for the slow model to finish, so guardrails let you quickly reject invalid inputs.
53 | 
54 | See the [`input_guardrails.py`](./input_guardrails.py) and [`output_guardrails.py`](./output_guardrails.py) files for examples.
55 | 


--------------------------------------------------------------------------------
/examples/research_bot/README.md:
--------------------------------------------------------------------------------
 1 | # Research bot
 2 | 
 3 | This is a simple example of a multi-agent research bot. To run it:
 4 | 
 5 | ```bash
 6 | python -m examples.research_bot.main
 7 | ```
 8 | 
 9 | ## Architecture
10 | 
11 | The flow is:
12 | 
13 | 1. User enters their research topic
14 | 2. `planner_agent` comes up with a plan to search the web for information. The plan is a list of search queries, with a search term and a reason for each query.
15 | 3. For each search item, we run a `search_agent`, which uses the Web Search tool to search for that term and summarize the results. These all run in parallel.
16 | 4. Finally, the `writer_agent` receives the search summaries, and creates a written report.
17 | 
18 | ## Suggested improvements
19 | 
20 | If you're building your own research bot, some ideas to add to this are:
21 | 
22 | 1. Retrieval: Add support for fetching relevant information from a vector store. You could use the File Search tool for this.
23 | 2. Image and file upload: Allow users to attach PDFs or other files, as baseline context for the research.
24 | 3. More planning and thinking: Models often produce better results given more time to think. Improve the planning process to come up with a better plan, and add an evaluation step so that the model can choose to improve its results, search for more stuff, etc.
25 | 4. Code execution: Allow running code, which is useful for data analysis.
26 | 


--------------------------------------------------------------------------------
/examples/research_bot/sample_outputs/product_recs.md:
--------------------------------------------------------------------------------
  1 | # Comprehensive Guide on Best Surfboards for Beginners: Transitioning, Features, and Budget Options
  2 | 
  3 | Surfing is not only a sport but a lifestyle that hooks its enthusiasts with the allure of riding waves and connecting with nature. For beginners, selecting the right surfboard is critical to safety, learning, and performance. This comprehensive guide has been crafted to walk through the essential aspects of choosing the ideal surfboard for beginners, especially those looking to transition from an 11-foot longboard to a shorter, more dynamic board. We discuss various board types, materials, design elements, and budget ranges, providing a detailed road map for both new surfers and those in the process of progression.
  4 | 
  5 | ---
  6 | 
  7 | ## Table of Contents
  8 | 
  9 | 1. [Introduction](#introduction)
 10 | 2. [Board Types and Design Considerations](#board-types-and-design-considerations)
 11 | 3. [Key Board Dimensions and Features](#key-board-dimensions-and-features)
 12 | 4. [Materials: Soft-Top vs. Hard-Top Boards](#materials-soft-top-vs-hard-top-boards)
 13 | 5. [Tips for Transitioning from Longboards to Shorter Boards](#tips-for-transitioning-from-longboards-to-shorter-boards)
 14 | 6. [Budget and Pricing Options](#budget-and-pricing-options)
 15 | 7. [Recommended Models and Buying Options](#recommended-models-and-buying-options)
 16 | 8. [Conclusion](#conclusion)
 17 | 9. [Follow-up Questions](#follow-up-questions)
 18 | 
 19 | ---
 20 | 
 21 | ## Introduction
 22 | 
 23 | Surfing is a dynamic sport that requires not only skill and technique but also the proper equipment. For beginners, the right surfboard can make the difference between a frustrating experience and one that builds confidence and enthusiasm. Many newcomers start with longboards due to their stability and ease of paddling; however, as skills develop, transitioning to a shorter board might be desirable for enhancing maneuverability and performance. This guide is designed for surfers who can already catch waves on an 11-foot board and are now considering stepping down to a more versatile option.
 24 | 
 25 | The overarching goal of this document is to help beginners identify which surfboard characteristics are most important, including board length, width, thickness, volume, and materials, while also considering factors like weight distribution, buoyancy, and control. We will also take a look at board types that are particularly welcoming for beginners and discuss gradual transitioning strategies.
 26 | 
 27 | ---
 28 | 
 29 | ## Board Types and Design Considerations
 30 | 
 31 | Choosing a board involves understanding the variety of designs available. Below are the main types of surfboards that cater to beginners and transitional surfers:
 32 | 
 33 | ### Longboards and Mini-Mals
 34 | 
 35 | Longboards, typically 8 to 11 feet in length, provide ample stability, smoother paddling, and are well-suited for wave-catching. Their generous volume and width allow beginners to build confidence when standing up and riding waves. Mini-mal or mini-malibus (often around 8 to 9 feet) are a popular bridge between the longboard and the more agile shortboard, offering both stability and moderate maneuverability, which makes them excellent for gradual progress.
 36 | 
 37 | ### Funboards and Hybrids
 38 | 
 39 | Funboards and hybrid boards blend the benefits of longboards and shortboards. They typically range from 6’6" to 8’0" in length, with extra volume and width that help preserve stability while introducing elements of sharper turning and improved agility. Hybrids are particularly helpful for surfers transitioning from longboards, as they maintain some of the buoyancy and ease of catching waves, yet offer a taste of the performance found in smaller boards.
 40 | 
 41 | ### Shortboards
 42 | 
 43 | Shortboards emphasize performance, maneuverability, and a more responsive ride. However, they have less volume and require stronger paddling, quicker pop-up techniques, and more refined balance. For beginners, moving to a traditional shortboard immediately can be challenging. It is generally advised to make a gradual transition, potentially starting with a funboard or hybrid before making a direct leap to a performance shortboard.
 44 | 
 45 | ---
 46 | 
 47 | ## Key Board Dimensions and Features
 48 | 
 49 | When selecting a beginner surfboard, several key dimensions and features drastically affect performance, ease of learning, and safety:
 50 | 
 51 | ### Length and Width
 52 | 
 53 | -   **Length**: Starting with an 8 to 9-foot board is ideal. Longer boards offer enhanced stability and improved paddling capabilities. Gradual downsizing is recommended if you plan to move from an 11-foot board.
 54 | -   **Width**: A board with a width over 20 inches provides greater stability and facilitates balance, especially vital for beginners.
 55 | 
 56 | ### Thickness and Volume
 57 | 
 58 | -   **Thickness**: Typically around 2.5 to 3 inches. Thicker decks increase buoyancy, allowing the surfer to paddle easier while catching waves.
 59 | -   **Volume**: Measured in liters, volume is critical in understanding a board's flotation capacity. Higher volumes (e.g., 60-100 liters) are essential for beginners as they make the board more forgiving and stable. Suitable volumes might vary according to the surfer’s weight and experience level.
 60 | 
 61 | ### Nose and Tail Shape
 62 | 
 63 | -   **Nose Shape**: A wide, rounded nose expands the board’s planing surface, which can help in catching waves sooner and maintaining stability as you ride.
 64 | -   **Tail Design**: Square or rounded tails are generally recommended as they enhance stability and allow for controlled turns, essential during the learning phase.
 65 | 
 66 | ### Rocker
 67 | 
 68 | -   **Rocker**: This is the curvature of the board from nose to tail. For beginners, a minimal or relaxed rocker provides better stability and ease during paddling. A steeper rocker might be introduced progressively as the surfer’s skills improve.
 69 | 
 70 | ---
 71 | 
 72 | ## Materials: Soft-Top vs. Hard-Top Boards
 73 | 
 74 | The material composition of a surfboard is a crucial factor in determining its performance, durability, and safety. Beginners have two primary choices:
 75 | 
 76 | ### Soft-Top (Foam) Boards
 77 | 
 78 | Soft-top boards are constructed almost entirely from foam. Their attributes include:
 79 | 
 80 | -   **Safety and Forgiveness**: The foam construction minimizes injury upon impact which is advantageous for beginners who might fall frequently.
 81 | -   **Stability and Buoyancy**: These boards typically offer greater buoyancy due to their softer material and thicker construction, easing the initial learning process.
 82 | -   **Maintenance**: They often require less maintenance—there is typically no need for waxing and they are more resistant to dings and scratches.
 83 | 
 84 | However, as a surfer’s skills progress, a soft-top might limit maneuverability and overall performance.
 85 | 
 86 | ### Hard-Top Boards
 87 | 
 88 | Hard-tops, in contrast, offer a more traditional surfboard feel. They generally rely on a foam core encased in resin, with two prevalent combinations:
 89 | 
 90 | -   **PU (Polyurethane) Core with Polyester Resin**: This combination gives a classic feel and is relatively economical; however, these boards can be heavier and, as they age, more prone to damage.
 91 | -   **EPS (Expanded Polystyrene) Core with Epoxy Resin**: Lightweight and durable, EPS boards are often more buoyant and resistant to damage, although they usually carry a higher price tag and may be less forgiving.
 92 | 
 93 | Deciding between soft-top and hard-top boards often depends on a beginner’s progression goals, overall comfort, and budget constraints.
 94 | 
 95 | ---
 96 | 
 97 | ## Tips for Transitioning from Longboards to Shorter Boards
 98 | 
 99 | For surfers who have mastered the basics on an 11-foot board, the transition to a shorter board requires careful consideration, patience, and incremental changes. Here are some key tips:
100 | 
101 | ### Gradual Downsizing
102 | 
103 | Experts recommend reducing the board length gradually—by about a foot at a time—to allow the body to adjust slowly to a board with less buoyancy and more responsiveness. This process helps maintain wave-catching ability and reduces the shock of transitioning to a very different board feel.
104 | 
105 | ### Strengthening Core Skills
106 | 
107 | Before transitioning, make sure your surfing fundamentals are solid. Focus on practicing:
108 | 
109 | -   **Steep Take-offs**: Ensure that your pop-up is swift and robust to keep pace with shorter boards that demand a rapid transition from paddling to standing.
110 | -   **Angling and Paddling Techniques**: Learn to angle your takeoffs properly to compensate for the lower buoyancy and increased maneuverability of shorter boards.
111 | 
112 | ### Experimenting with Rentals or Borrowed Boards
113 | 
114 | If possible, try out a friend’s shorter board or rent one for a day to experience firsthand the differences in performance. This practical trial can provide valuable insights and inform your decision before making a purchase.
115 | 
116 | ---
117 | 
118 | ## Budget and Pricing Options
119 | 
120 | Surfboards are available across a range of prices to match different budgets. Whether you are looking for an affordable beginner board or a more expensive model that grows with your skills, it’s important to understand what features you can expect at different price points.
121 | 
122 | ### Budget-Friendly Options
123 | 
124 | For those on a tight budget, several entry-level models offer excellent value. Examples include:
125 | 
126 | -   **Wavestorm 8' Classic Pinline Surfboard**: Priced affordably, this board is popular for its ease of use, ample volume, and forgiving nature. Despite its low cost, it delivers the stability needed to get started.
127 | -   **Liquid Shredder EZ Slider Foamie**: A smaller board catering to younger or lighter surfers, this budget option provides easy paddling and a minimal risk of injury due to its soft construction.
128 | 
129 | ### Moderate Price Range
130 | 
131 | As you move into the intermediate range, boards typically become slightly more specialized in their design, offering features such as improved stringer systems or versatile fin setups. These are excellent for surfers who wish to continue progressing their skills without compromising stability. Many surfboard packages from retailers also bundle a board with essential accessories like board bags, leashes, and wax for additional savings.
132 | 
133 | ### Higher-End Models and Transitional Packages
134 | 
135 | For surfers looking for durability, performance, and advanced design features, investing in an EPS/epoxy board might be ideal. Although they come at a premium, these boards are lightweight, strong, and customizable with various fin configurations. Some options include boards from brands like South Bay Board Co. and ISLE, which combine high-quality construction with beginner-friendly features that help mediate the transition from longboard to shortboard performance.
136 | 
137 | ---
138 | 
139 | ## Recommended Models and Buying Options
140 | 
141 | Based on extensive research and community recommendations, here are some standout models and tips on where to buy:
142 | 
143 | ### Recommended Models
144 | 
145 | -   **South Bay Board Co. 8'8" Heritage**: Combining foam and resin construction, this board is ideal for beginners who need stability and a forgiving surface. Its 86-liter volume suits both lightweight and somewhat heavier surfers.
146 | -   **Rock-It 8' Big Softy**: With a high volume and an easy paddling profile, this board is designed for beginners, offering ample buoyancy to smooth out the learning curve.
147 | -   **Wave Bandit EZ Rider Series**: Available in multiple lengths (7', 8', 9'), these boards offer versatility, with construction features that balance the stability of longboards and the agility required for shorter boards.
148 | -   **Hybrid/Funboards Like the Poacher Funboard**: Perfect for transitioning surfers, these boards blend the ease of catching waves with the capability for more dynamic maneuvers.
149 | 
150 | ### Buying Options
151 | 
152 | -   **Surf Shops and Local Retailers**: Traditional surf shops allow you to test different boards, which is ideal for assessing the board feel and condition—especially if you are considering a used board.
153 | -   **Online Retailers and Marketplaces**: Websites like Evo, Surfboards Direct, and even local online marketplaces like Craigslist and Facebook Marketplace provide options that range from new to gently used boards. Always inspect reviews and verify seller policies before purchase.
154 | -   **Package Deals and Bundles**: Many retailers offer bundled packages that include not just the board, but also essentials like a leash, wax, fins, and board bags. These packages can be more cost-effective and are great for beginners who need a complete surf kit.
155 | 
156 | ---
157 | 
158 | ## Conclusion
159 | 
160 | Selecting the right surfboard as a beginner is about balancing various factors: stability, buoyancy, maneuverability, and budget.
161 | 
162 | For those who have honed the basics using an 11-foot longboard, the transition to a shorter board should be gradual. Start by focusing on boards that preserve stability—such as funboards and hybrids—before moving to the more performance-oriented shortboards. Key characteristics like board length, width, thickness, volume, and material profoundly influence your surfing experience. Soft-top boards provide a forgiving entry point, while hard-top boards, especially those with EPS cores and epoxy resin, offer benefits for more advanced progression despite the increased learning curve.
163 | 
164 | Emphasizing fundamentals like proper pop-up technique and effective paddle work will ease the transition and ensure that the new board complements your evolving skills. Additionally, understanding the pricing spectrum—from budget-friendly models to premium options—allows you to make an informed purchase that suits both your financial and performance needs.
165 | 
166 | With a thoughtful approach to board selection, you can enhance your learning curve, enjoy safer sessions in the water, and ultimately develop the skills necessary to master the diverse challenges surfing presents. Whether your goal is to ride gentle waves or eventually experiment with sharper turns and dynamic maneuvers, choosing the right board is your first step towards a rewarding and sustainable surfing journey.
167 | 
168 | ---
169 | 
170 | ## Follow-up Questions
171 | 
172 | 1. What is your current budget range for a new surfboard, or are you considering buying used?
173 | 2. How frequently do you plan to surf, and in what type of wave conditions?
174 | 3. Are you interested in a board that you can grow into as your skills progress, or do you prefer one that is more specialized for certain conditions?
175 | 4. Would you be interested in additional equipment bundles (like fins, leashes, boards bags) offered by local retailers or online shops?
176 | 5. Have you had the opportunity to test ride any boards before, and what feedback did you gather from that experience?
177 | 
178 | ---
179 | 
180 | With this detailed guide, beginners should now have a comprehensive understanding of the surfboard market and the key factors influencing board performance, safety, and ease of progression. Happy surfing, and may you find the perfect board that rides the waves as beautifully as your passion for the sport!
181 | 


--------------------------------------------------------------------------------
/examples/research_bot/sample_outputs/vacation.md:
--------------------------------------------------------------------------------
  1 | Report: # Caribbean Adventure in April: Surfing, Hiking, and Water Sports Exploration
  2 | 
  3 | The Caribbean is renowned for its crystal-clear waters, vibrant culture, and diverse outdoor activities. April is an especially attractive month for visitors: warm temperatures, clear skies, and the promise of abundant activities. This report explores the best Caribbean destinations in April, with a focus on optimizing your vacation for surfing, hiking, and water sports.
  4 | 
  5 | ---
  6 | 
  7 | ## Table of Contents
  8 | 
  9 | 1. [Introduction](#introduction)
 10 | 2. [Why April is the Perfect Time in the Caribbean](#why-april-is-the-perfect-time-in-the-caribbean)
 11 | 3. [Surfing in the Caribbean](#surfing-in-the-caribbean)
 12 |     - 3.1 [Barbados: The Tale of Two Coasts](#barbados-the-tale-of-two-coasts)
 13 |     - 3.2 [Puerto Rico: Rincón and Beyond](#puerto-rico-rinc%C3%B3n-and-beyond)
 14 |     - 3.3 [Dominican Republic and Other Hotspots](#dominican-republic-and-other-hotspots)
 15 | 4. [Hiking Adventures Across the Caribbean](#hiking-adventures-across-the-caribbean)
 16 |     - 4.1 [Trekking Through Tropical Rainforests](#trekking-through-tropical-rainforests)
 17 |     - 4.2 [Volcanic Peaks and Rugged Landscapes](#volcanic-peaks-and-rugged-landscapes)
 18 | 5. [Diverse Water Sports Experiences](#diverse-water-sports-experiences)
 19 |     - 5.1 [Snorkeling, Diving, and Jet Skiing](#snorkeling-diving-and-jet-skiing)
 20 |     - 5.2 [Kiteboarding and Windsurfing](#kiteboarding-and-windsurfing)
 21 | 6. [Combining Adventures: Multi-Activity Destinations](#combining-adventures-multi-activity-destinations)
 22 | 7. [Practical Advice and Travel Tips](#practical-advice-and-travel-tips)
 23 | 8. [Conclusion](#conclusion)
 24 | 
 25 | ---
 26 | 
 27 | ## Introduction
 28 | 
 29 | Caribbean vacations are much more than just beach relaxation; they offer adventure, exploration, and a lively cultural tapestry waiting to be discovered. For travelers seeking an adrenaline-filled getaway, April provides optimal conditions. This report synthesizes diverse research findings and travel insights to help you create an itinerary that combines the thrill of surfing, the challenge of hiking, and the excitement of water sports.
 30 | 
 31 | Whether you're standing on the edge of a powerful reef break or trekking through lush tropical landscapes, the Caribbean in April invites you to dive into nature, adventure, and culture. The following sections break down the best destinations and activities, ensuring that every aspect of your trip is meticulously planned for an unforgettable experience.
 32 | 
 33 | ---
 34 | 
 35 | ## Why April is the Perfect Time in the Caribbean
 36 | 
 37 | April stands at the crossroads of seasons in many Caribbean destinations. It marks the tail end of the dry season, ensuring:
 38 | 
 39 | -   **Consistent Warm Temperatures:** Average daytime highs around 29°C (84°F) foster comfortable conditions for both land and water activities.
 40 | -   **Pleasant Sea Temperatures:** With sea temperatures near 26°C (79°F), swimmers, surfers, and divers are treated to inviting waters.
 41 | -   **Clear Skies and Minimal Rainfall:** Crisp, blue skies make for excellent visibility during snorkeling and diving, as well as clear panoramic views while hiking.
 42 | -   **Festivals and Cultural Events:** Many islands host seasonal festivals such as Barbados' Fish Festival and Antigua's Sailing Week, adding a cultural layer to your vacation.
 43 | 
 44 | These factors create an ideal backdrop for balancing your outdoor pursuits, whether you’re catching epic waves, trekking rugged trails, or partaking in water sports.
 45 | 
 46 | ---
 47 | 
 48 | ## Surfing in the Caribbean
 49 | 
 50 | Surfing in the Caribbean offers diverse wave experiences, ranging from gentle, beginner-friendly rollers to powerful reef breaks that challenge even seasoned surfers. April, in particular, provides excellent conditions for those looking to ride its picturesque waves.
 51 | 
 52 | ### Barbados: The Tale of Two Coasts
 53 | 
 54 | Barbados is a prime destination:
 55 | 
 56 | -   **Soup Bowl in Bathsheba:** On the east coast, the Soup Bowl is famous for its consistent, powerful waves. This spot attracts experienced surfers who appreciate its challenging right-hand reef break with steep drops, providing the kind of performance wave rarely found elsewhere.
 57 | -   **Freights Bay:** On the south coast, visitors find more forgiving, gentle wave conditions. Ideal for beginners and longboarders, this spot offers the perfect balance for those still mastering their craft.
 58 | 
 59 | Barbados not only excels in its surfing credentials but also complements the experience with a rich local culture and events in April, making it a well-rounded destination.
 60 | 
 61 | ### Puerto Rico: Rincón and Beyond
 62 | 
 63 | Rincón in Puerto Rico is hailed as the Caribbean’s surfing capital:
 64 | 
 65 | -   **Diverse Breaks:** With spots ranging from challenging reef breaks such as Tres Palmas and Dogman's to more inviting waves at Domes and Maria's, Puerto Rico offers a spectrum for all surfing skill levels.
 66 | -   **Local Culture:** Aside from its surf culture, the island boasts vibrant local food scenes, historic sites, and exciting nightlife, enriching your overall travel experience.
 67 | 
 68 | In addition, Puerto Rico’s coasts often feature opportunities for hiking and other outdoor adventures, making it an attractive option for multi-activity travelers.
 69 | 
 70 | ### Dominican Republic and Other Hotspots
 71 | 
 72 | Other islands such as the Dominican Republic, with Playa Encuentro on its north coast, provide consistent surf year-round. Highlights include:
 73 | 
 74 | -   **Playa Encuentro:** A hotspot known for its dependable breaks, ideal for both intermediate and advanced surfers during the cooler months of October to April.
 75 | -   **Jamaica and The Bahamas:** Jamaica’s Boston Bay offers a mix of beginner and intermediate waves, and The Bahamas’ Surfer’s Beach on Eleuthera draws parallels to the legendary surf spots of Hawaii, especially during the winter months.
 76 | 
 77 | These destinations not only spotlight surfing but also serve as gateways to additional outdoor activities, ensuring there's never a dull moment whether you're balancing waves with hikes or cultural exploration.
 78 | 
 79 | ---
 80 | 
 81 | ## Hiking Adventures Across the Caribbean
 82 | 
 83 | The Caribbean's topography is as varied as it is beautiful. Its network of hiking trails traverses volcanic peaks, ancient rainforests, and dramatic coastal cliffs, offering breathtaking vistas to intrepid explorers.
 84 | 
 85 | ### Trekking Through Tropical Rainforests
 86 | 
 87 | For nature enthusiasts, the lush forests of the Caribbean present an immersive encounter with biodiversity:
 88 | 
 89 | -   **El Yunque National Forest, Puerto Rico:** The only tropical rainforest within the U.S. National Forest System, El Yunque is rich in endemic species such as the Puerto Rican parrot and the famous coquí frog. Trails like the El Yunque Peak Trail and La Mina Falls Trail provide both challenging hikes and scenic rewards.
 90 | -   **Virgin Islands National Park, St. John:** With over 20 well-defined trails, this park offers hikes that reveal historical petroglyphs, colonial ruins, and stunning coastal views along the Reef Bay Trail.
 91 | 
 92 | ### Volcanic Peaks and Rugged Landscapes
 93 | 
 94 | For those seeking more rugged challenges, several destinations offer unforgettable adventures:
 95 | 
 96 | -   **Morne Trois Pitons National Park, Dominica:** A UNESCO World Heritage Site showcasing volcanic landscapes, hot springs, the famed Boiling Lake, and lush trails that lead to hidden waterfalls.
 97 | -   **Gros Piton, Saint Lucia:** The iconic hike up Gros Piton provides a moderately challenging trek that ends with panoramic views of the Caribbean Sea, a truly rewarding experience for hikers.
 98 | -   **La Soufrière, St. Vincent:** This active volcano not only offers a dynamic hiking environment but also the opportunity to observe the ongoing geological transformations up close.
 99 | 
100 | Other noteworthy hiking spots include the Blue Mountains in Jamaica for coffee plantation tours and expansive views, as well as trails in Martinique around Montagne Pelée, which combine historical context with natural beauty.
101 | 
102 | ---
103 | 
104 | ## Diverse Water Sports Experiences
105 | 
106 | While surfing and hiking attract a broad range of adventurers, the Caribbean also scores high on other water sports. Whether you're drawn to snorkeling, jet skiing, or wind- and kiteboarding, the islands offer a plethora of aquatic activities.
107 | 
108 | ### Snorkeling, Diving, and Jet Skiing
109 | 
110 | Caribbean waters teem with life and color, making them ideal for underwater exploration:
111 | 
112 | -   **Bonaire:** Its protected marine parks serve as a magnet for divers and snorkelers. With vibrant coral reefs and diverse marine species, Bonaire is a top destination for those who appreciate the underwater world.
113 | -   **Cayman Islands:** Unique attractions such as Stingray City provide opportunities to interact with friendly stingrays in clear, calm waters. Additionally, the Underwater Sculpture Park is an innovative blend of art and nature.
114 | -   **The Bahamas:** In places like Eleuthera, excursions often cater to families and thrill-seekers alike. Options include jet ski rentals, where groups can explore hidden beaches and pristine coves while enjoying the vibrant marine life.
115 | 
116 | ### Kiteboarding and Windsurfing
117 | 
118 | Harnessing the steady trade winds and warm Caribbean waters, several islands have become hubs for kiteboarding and windsurfing:
119 | 
120 | -   **Aruba:** Known as "One Happy Island," Aruba’s Fisherman's Huts area provides consistent winds, perfect for enthusiasts of windsurfing and kiteboarding alike.
121 | -   **Cabarete, Dominican Republic and Silver Rock, Barbados:** Both destinations benefit from reliable trade winds, making them popular among kitesurfers. These spots often combine water sports with a lively beach culture, ensuring that the fun continues on land as well.
122 | 
123 | Local operators provide equipment rental and lessons, ensuring that even first-time adventurers can safely and confidently enjoy these exciting sports.
124 | 
125 | ---
126 | 
127 | ## Combining Adventures: Multi-Activity Destinations
128 | 
129 | For travelers seeking a comprehensive vacation where surfing, hiking, and water sports converge, several Caribbean destinations offer the best of all worlds.
130 | 
131 | -   **Puerto Rico:** With its robust surf scene in Rincón, world-class hiking in El Yunque, and opportunities for snorkeling and jet skiing in San Juan Bay, Puerto Rico is a true multi-adventure destination.
132 | -   **Barbados:** In addition to the surf breaks along its coasts, Barbados offers a mix of cultural events, local cuisine, and even hiking excursions to scenic rural areas, making for a well-rounded experience.
133 | -   **Dominican Republic and Jamaica:** Both are renowned not only for their consistent surf conditions but also for expansive hiking trails and water sports. From the rugged landscapes of the Dominican Republic to Jamaica’s blend of cultural history and natural exploration, these islands allow travelers to mix and match activities seamlessly.
134 | 
135 | Group tours and local guides further enhance these experiences, providing insider tips, safe excursions, and personalized itineraries that cater to multiple interests within one trip.
136 | 
137 | ---
138 | 
139 | ## Practical Advice and Travel Tips
140 | 
141 | ### Weather and Timing
142 | 
143 | -   **Optimal Climate:** April offers ideal weather conditions across the Caribbean. With minimal rainfall and warm temperatures, it is a great time to schedule outdoor activities.
144 | -   **Surfing Seasons:** While April marks the end of the prime surf season in some areas (like Rincón in Puerto Rico), many destinations maintain consistent conditions during this month.
145 | 
146 | ### Booking and Costs
147 | 
148 | -   **Surfing Lessons:** Expect to pay between $40 and $110 per session depending on the location. For instance, Puerto Rico typically charges around $75 for beginner lessons, while group lessons in the Dominican Republic average approximately $95.
149 | -   **Equipment Rentals:** Pricing for jet ski, surfboard, and snorkeling equipment may vary. In the Bahamas, an hour-long jet ski tour might cost about $120 per group, whereas a similar experience might be available at a lower cost in other regions.
150 | -   **Accommodations:** Prices also vary by island. Many travelers find that even affordable stays do not skimp on amenities, allowing you to invest more in guided excursions and local experiences.
151 | 
152 | ### Cultural Considerations
153 | 
154 | -   **Festivals and Events:** Check local event calendars. Destinations like Barbados and Antigua host festivals in April that combine cultural heritage with festive outdoor activities.
155 | -   **Local Cuisine:** Incorporate food tours into your itinerary. Caribbean cuisine—with its fusion of flavors—can be as adventurous as the outdoor activities.
156 | 
157 | ### Health and Safety
158 | 
159 | -   **Staying Hydrated:** The warm temperatures demand that you stay properly hydrated. Always carry water, especially during long hikes.
160 | -   **Sun Protection:** Use sunscreen, hats, and sunglasses to protect yourself during extended periods outdoors on both land and water.
161 | -   **Local Guides:** Utilize local tour operators for both hiking and water sports. Their expertise not only enriches your experience but also ensures safety in unfamiliar terrain or water bodies.
162 | 
163 | ---
164 | 
165 | ## Conclusion
166 | 
167 | The Caribbean in April is a haven for adventure seekers. With its pristine beaches, diverse ecosystems, and rich cultural tapestry, it offers something for every type of traveler. Whether you're chasing the perfect wave along the shores of Barbados and Puerto Rico, trekking through the lush landscapes of El Yunque or Morne Trois Pitons, or engaging in an array of water sports from snorkeling to kiteboarding, your ideal vacation is only a booking away.
168 | 
169 | This report has outlined the best destinations and provided practical advice to optimize your vacation for surfing, hiking, and water sports. By considering the diverse offerings—from epic surf breaks and challenging hiking trails to vibrant water sports—the Caribbean stands out as a multi-adventure destination where every day brings a new experience.
170 | 
171 | Plan carefully, pack wisely, and get ready to explore the vibrant mosaic of landscapes and activities that make the Caribbean in April a truly unforgettable adventure.
172 | 
173 | Happy travels!
174 | 
175 | ---
176 | 
177 | _References available upon request. Many insights were drawn from trusted sources including Lonely Planet, TravelPug, and various Caribbean-centric exploration sites, ensuring a well-rounded and practical guide for your vacation planning._
178 | 


--------------------------------------------------------------------------------
