# Agy Podcast Generator: Agentic Coding Demo Script

This document provides a step-by-step guide to reproducing the "Agy Podcast Generator" demo using Antigravity. This demo showcases how to go from a functional specification to a fully tested, working Next.js application using Google's Gemini LLM and Text-to-Speech APIs, demonstrating planning, execution, and verification agentic workflows.

## 1. Preparation
Before starting the demo, ensure you have the following ready:
*   **Download/Install Antigravity**: Ensure the agent environment is set up and running on your device.
*   **Generate an API Key**: Obtain a Gemini API Key to use the `@google/genai` SDK.
*   **Generate ADC Credentials**: Make sure you have Google Cloud Application Default Credentials (ADC) configured on your machine, or create a service account JSON key for the Text-to-Speech API (`GOOGLE_APPLICATION_CREDENTIALS`).

## 2. Setup the Workspace
Clone the starting repository which contains the functional specifications and the Agent Skill:
```bash
git clone https://github.com/ggalloro/agy-podcast-generator
cd agy-podcast-generator
```

## 3. The Demo Flow

### Step 1: Context and Skills
*   **Show the Functional Specification**: Open `podcast-generator-functional-spec.md` and briefly explain the goal: an app that takes RSS feeds, fetches articles, summarizes them, and converts them to an audio podcast.
*   **Show the Agent Skill**: Open `.agent/skills/js_genai/SKILL.md`. Explain that this skill teaches the agent how to correctly use the new `@google/genai` JS SDK by fetching the latest guidelines. Refer to the Agent Skill documentation to show how this steers the agent's code generation.

### Step 2: The Initial Prompt
Use the following prompt to kick off the agent:
> "Build the application described in @podcast-generator-functional-spec.md use Next.js as the framework, Tailwind CSS for the UI, use Gemini as the AI services for summarization and Google text to speech Chirp voices for audio generation. Test it with the agent browser until it works as expected"

### Step 3: Planning Phase
*   The agent will read the specs and the skill, and begin the **PLANNING** phase.
*   **Show the "Task" artifact**: Point out how the agent breaks down the work into a structured checklist (e.g., Set up Next.js, UI, API Routes, Synthesis, Testing).
*   **Show the "Implementation Plan"**: Wait for the agent to present the proposed changes and ask for your review.

### Step 4: User Review and Environment Variables
Before approving the plan, you need to create the environment variables file and provide feedback to the agent.
1.  **Create `.env.local`**: In the root of the workspace, create an `.env.local` file and add your keys:
    ```env
    GEMINI_API_KEY="your_api_key_here"
    GOOGLE_APPLICATION_CREDENTIALS="/path/to/your/gcp-key.json"
    ```
2.  **Provide Feedback**: Select the relevant sections in the Implementation Plan (or reply in the chat) and make these two specific comments:
    *   *"I put the GEMINI_API_KEY and GOOGLE_APPLICATION_CREDENTIALS environment variables valued with the credentials in the .env.local file I created in the root of the workspace, use those."*
    *   *"The main application page shall display a high quality hero image featuring a robot agent reading the news in a TV studio. Generate it with nano banana."*

### Step 5: Execution Phase
*   **Proceed with the plan**: Tell the agent to continue.
*   The agent will now switch to the **EXECUTION** phase. It will scaffold the Next.js app, install dependencies, and write the frontend/backend code.
*   **Show the Image Generation**: Highlight the moment the agent uses its image generation tool (Nano Banana / Gemini 2.5 Flash Image) to create the requested hero image and saves it to the public directory.
*   **Show the Output**: Once the execution is complete, you can review the generated code in `page.tsx` and the API routes.

### Step 6: Verification Phase
*   The agent will automatically (or upon prompting) switch to the **VERIFICATION** phase.
*   It will start the Next.js development server (`npm run dev`).
*   **Show the Testing with the Browser Agent**: Watch as the browser subagent autonomously navigates to `localhost:3000`, adds an RSS feed (e.g., The Verge), clicks "Generate Podcast", and waits for the audio to be synthesized and added to the library.
*   Once verified, the agent completes the task!
