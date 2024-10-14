# YouTube Blog Generator

This project automates the process of generating blog content based on YouTube videos from specific channels. Using a team of intelligent agents, this system retrieves YouTube transcripts and transforms the content into engaging blog posts, ideal for creating tech blogs from video reviews and discussions.

## Features

- **YouTube Video Search and Transcription**: Automatically retrieves the transcription of the specified YouTube video from a channel.
- **Content Research**: Analyzes the video content to generate a detailed research report.
- **Blog Writing**: Uses AI to write a well-structured blog post based on the research.

## Installation

To run this project, make sure you have Python installed and set up a virtual environment. Then, follow the steps below:

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/yt-blog-generator.git
Navigate to the project directory:

bash
Copy code
cd yt-blog-generator
Set up a virtual environment:

bash
Copy code
python3 -m venv venv
Activate the virtual environment:

On macOS/Linux:

bash
Copy code
source venv/bin/activate
On Windows:

bash
Copy code
venv\Scripts\activate
Install the required dependencies:

bash
Copy code
pip install -r requirements.txt
Usage
1. Setting up Environment Variables
Make sure to create a .env file at the root of the project and set your OpenAI API key and any other environment variables. Example .env:

env
Copy code
OPENAI_API_KEY=your_openai_api_key
OPENAI_MODEL_NAME=gpt-4-0125-preview
2. Running the Blog Generator
The project uses agents to research and write blog posts based on the YouTube videos from a specific channel.

Research Task: Fetches video details and generates a research report.
Writing Task: Summarizes the research report and creates a blog post.
You can start the process by executing the following command:

bash
Copy code
python crew.py
The system will generate a blog post based on the video topic specified in the crew.py file. By default, the topic is set to "Samsung Galaxy Ring Review: I Wanted to Love It!", but you can modify this by changing the inputs dictionary in crew.py.

3. Output
Once the process is complete, the generated blog content will be saved in a file called new-blog-post.md.

Project Structure
bash
Copy code
.
├── __pycache__
├── db
├── venv
├── .env                 # Environment variables file (not included in repo)
├── .gitignore           # Git ignore file
├── agents.py            # AI agents for research and writing
├── crew.py              # Main process to manage tasks and agent execution
├── requirements.txt     # Python dependencies
├── tasks.py             # Task definitions for research and blog writing
├── tools.py             # YouTube search tool for fetching transcripts
agents.py: Defines the agents that handle research and writing tasks.
crew.py: Configures and executes the process using the agents and tasks.
tasks.py: Contains the specific research and writing tasks.
tools.py: Includes a tool to search YouTube channels and retrieve transcripts.
requirements.txt: Lists all the required dependencies for the project.
Dependencies
crewai
crewai_tools
load_dotenv
langchain-huggingface
youtube-transcript-api==0.6.1
yt_dlp==2023.11.14
These are automatically installed when you run pip install -r requirements.txt.

How It Works
YouTube Search: The system uses the YoutubeChannelSearchTool to search for a video on a specific YouTube channel.
Research Agent: The blog_researcher agent analyzes the YouTube video and generates a detailed research report on the given topic.
Blog Writing Agent: The blog_writer agent summarizes the research report and generates a blog post, making sure to structure the content for readability and engagement.
Customization
You can customize the agents, tasks, and the YouTube channel by modifying the files:

Changing the YouTube Channel: Edit the channel handle in tools.py.
Modifying the Tasks: Adjust the task descriptions and outputs in tasks.py to suit your blog style.
Changing the Blog Topic: Update the inputs parameter in crew.py to set a different video topic for the research and writing tasks.
