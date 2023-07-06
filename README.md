# OpenAI Multi-model Query Script

This script is designed to take a list of prompts related to the fundamentals and building blocks of life, submit them to various OpenAI models for completion, and store the results.

## How to use

First, install the necessary libraries:

pip install openai

Then, run the script:

python GTP4All_Playground.py

The script will generate output JSON files containing the results from each model for each prompt. Each file is named according to the format `<model_name>_output_<max_tokens>_tokens.json`, and is stored in a directory corresponding to the prompt.

## Notes

* The script interacts with a local OpenAI Language Model (LLM) instance running at `http://localhost:4891/v1`. Adjust the `openai.api_base` as needed.
* An API key is not required for local LLMs, but if you're running this against a remote OpenAI API, be sure to set your `openai.api_key`.
* The script uses a custom `sanitize_directory_name` function to remove any non-alphanumeric characters from the prompt to create a directory name.
* The `max_tokens` parameter, controlling the length of the response, is varied between runs. This allows the script to generate both short and long answers.
* The response from the OpenAI API is captured, converted to JSON, and saved to the corresponding file.
* If an error occurs while running a model, the error will be printed and the script will move on to the next model.
