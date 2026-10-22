# import os
from google import genai

client = genai.Client(
    api_key=os.environ.get("GEMINI_API_KEY"),
)

generation_config = {
    'max_output_tokens': 65536,
    'thinking_level': 'medium',
}

interaction = client.interactions.create(
    model='models/gemini-3.8-flash',
    input="""INSERT_INPUT_HERE""",
    generation_config=generation_config,
)

print(interaction.output_text)


