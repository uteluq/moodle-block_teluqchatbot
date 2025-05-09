

# Moodle Block TeluqChatbot

**TeluqChatbot** is a Moodle block plugin designed to enhance distance learning by providing an adaptive and innovative chatbot solution. Integrated into the Moodle platform, it supports three distinct user roles—**Learner**, **Teacher**, and **Administrative Manager**—to facilitate course interactions, content management, and plugin configuration. This plugin leverages **Retrieval-Augmented Generation (RAG)** to deliver precise, context-aware responses based on course materials, improving the learning experience for users.

## Features

### Learner Role
- **Interactive Q&A**: Learners can ask questions about course content, receive clarifications, revise exercises, and get study method suggestions via a user-friendly interface.
- **Contextual Responses**: With RAG enabled, the chatbot provides accurate, course-specific answers by retrieving relevant information from uploaded course materials.


### Teacher Role
- **Course Upload**: Teachers can upload multiple PDF course resources simultaneously, which the chatbot uses to generate informed responses.
- **Prompt Customization**: Teachers can modify the default prompt to tailor the chatbot’s behavior, supported by a provided Prompt Design Guide.
- **Testing Functionality**: Teachers can test the chatbot by posing questions to verify its performance with uploaded resources.




### Administrative Manager Role
- **Plugin Configuration**: Admins configure the plugin via Moodle’s site administration interface, setting up API keys for services like OpenAI, Cohere Embedding, Adobe PDF Services, and Weaviate.
- **Seamless Integration**: The plugin is accessible under the “Plugins” section of Moodle’s admin panel for easy management.



### RAG Integration
- **With RAG**: Enhances response accuracy, relevance, and completeness by retrieving course-specific data from a vector database before generating answers.
- **Without RAG**: Provides general responses based on the model’s internal knowledge, suitable for quick interactions but less precise for course-specific queries.



## Installation

1. **Download the Plugin**:
   - Clone the repository: `git clone https://github.com/teluq/moodle-block_teluqchatbot.git`
   - Or download the ZIP file from the [Moodle Plugins Directory](#) (once published).

2. **Install in Moodle**:
   - Copy the `teluqchatbot` folder to the `/blocks/` directory of your Moodle installation.
   - Navigate to **Site Administration > Notifications** in Moodle to trigger the installation process.
   - Follow the on-screen instructions to complete the setup.

3. **Configure the Plugin**:
   - Go to **Site Administration > Plugins > Blocks > TeluqChatbot**.
   - Enter the required API keys for OpenAI, Cohere Embedding, Adobe PDF Services, and Weaviate.
   - Save the settings to activate the plugin.

## Usage

### For Learners
1. Access the chatbot block on a course page.
2. Pose questions related to course content in the provided text box.
3. Toggle between **RAG** and **non-RAG** modes to compare response quality if testing.

<img src="https://raw.githubusercontent.com/uteluq/moodle-block_teluqchatbot/main/screenshots/interface.png" alt="isolated" width="20%"/>


### For Teachers
1. From the chatbot interface, click **Upload Course** to add PDF resources.
2. Click **Modify Prompt** to customize the chatbot’s response behavior, referring to the Prompt Design Guide.
3. Test the chatbot by asking questions to ensure it aligns with course content.

<img src="https://raw.githubusercontent.com/uteluq/moodle-block_teluqchatbot/main/screenshots/rag.png" alt="isolated" width="20%"/>

<img src="https://raw.githubusercontent.com/uteluq/moodle-block_teluqchatbot/main/screenshots/prompt.png" alt="isolated" width="20%"/>


### For Admins
1. Access **Site Administration > Plugins > Blocks > TeluqChatbot**.
2. Configure API keys and other settings as needed.
3. Monitor plugin performance and ensure API services are operational.

<img src="https://raw.githubusercontent.com/uteluq/moodle-block_teluqchatbot/main/screenshots/keys.png" alt="isolated" width="20%"/>


## Testing and Validation

The plugin has been rigorously tested in both academic and AWS cloud environments to ensure robustness and scalability (see project report, Section 2). Key findings include:
- **RAG Mode**: Outperforms non-RAG mode in precision, relevance, completeness, and pedagogical utility, with clear, context-aware responses and no noticeable latency.
- **Non-RAG Mode**: Offers satisfactory clarity and speed but may provide less accurate or overly general responses for course-specific queries.

A detailed testing protocol will be published, with evaluation criteria including:
- Precision, relevance, clarity, and completeness of responses.
- Response time, dialogue coherence, and pedagogical utility.
- Comparative testing with and without RAG, using provided course PDFs.

## Requirements

- **Moodle Version**: Compatible with Moodle [specify version, e.g., 4.0+] (ensure compatibility with maintained versions as per [Moodle Releases](https://moodledev.io/general/releases)).
- **Database**: Tested with MySQL and PostgreSQL, using Moodle’s [Data Manipulation API](https://moodledev.io/docs/5.1/apis/core/dml).
- **API Services**:
  - OpenAI API for language model support.
  - Cohere Embedding for vector database integration.
  - Adobe PDF Services for processing uploaded course materials.
  - Weaviate for vector database storage and retrieval.
- **Server**: Deployable on standard Moodle servers or AWS for scalability.
- **Empathy Evaluation**: Assessing perceived empathy in learner interactions with the chatbot.


### Web Services

The **TeluqChatbot** Moodle block plugin integrates several web services to support its functionality, as outlined in the project report. These services are configured via the plugin's administrative interface and are essential for processing course materials, generating responses, and enabling Retrieval-Augmented Generation (RAG). Below is a list of the web services used:

- **OpenAI API**:
  - **Purpose**: Drives the language model to generate responses for user queries in both RAG and non-RAG modes.
  - **Configuration**: Requires an API key entered in the plugin’s admin settings (see Figure 7).

- **Cohere Embedding API**:
  - **Purpose**: Creates embeddings for course content, enabling storage and retrieval in a vector database for RAG-based contextual responses.
  - **Configuration**: Requires an API key entered in the plugin’s admin settings.

- **Adobe PDF Services**:
  - **Purpose**: Processes uploaded PDF course materials to extract content for response generation.
  - **Configuration**: Requires a client ID and client secret entered in the plugin’s admin settings.

- **Weaviate**:
  - **Purpose**: Acts as the vector database to store content embeddings, supporting the retrieval component of RAG for contextual responses.
  - **Configuration**: Requires API key(s) entered in the plugin’s admin settings (note: multiple entries in the report may indicate an OCR error or distinct keys).

- Configuration is managed through **Site Administration > Plugins > Blocks > TeluqChatbot** in Moodle.


## Contributing

Contributions are welcome! To contribute:
1. Fork the repository: `https://github.com/teluq/moodle-block_teluqchatbot`.
2. Create a feature branch: `git checkout -b feature/your-feature`.
3. Commit changes: `git commit -m "Add your feature"`.
4. Push to the branch: `git push origin feature/your-feature`.
5. Open a pull request.

Please adhere to Moodle’s [Coding Style](https://moodledev.io/general/development/policies/codingstyle) and submit issues via the [GitHub Issues](https://github.com/teluq/moodle-block_teluqchatbot/issues) page.

## License

This plugin is licensed under the **GNU General Public License v3.0 or later** (GPLv3+). See the [LICENSE](LICENSE) file for details.

## Support

For issues, feature requests, or questions:
- File an issue on the [GitHub Issues](https://github.com/teluq/moodle-block_teluqchatbot/issues) page.
- Refer to the [Moodle Tracker](https://tracker.moodle.org/) for broader Moodle-related support.
- Consult the [Moodle Documentation](https://docs.moodle.org/) or the plugin’s [Prompt Design Guide](#) for specific guidance.

## Acknowledgments

Developed under the **PROJET R&I 2024 Composante 2** by the Université TÉLUQ and the Université Gaston-Berger. Special thanks to the Agence Universitaire de la Francophonie (AUF) for supporting this initiative.

