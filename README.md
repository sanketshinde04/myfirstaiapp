# Tweet Generator 

A powerful AI-powered tweet generation application built with Streamlit, supporting both **Google's Gemini AI** and **OpenAI's GPT** models. Generate engaging tweets on any topic with just a few clicks!

## 🚀 Features

- **AI-Powered Generation**: Uses Google's Gemini 2.5 Flash and OpenAI's GPT-4o-mini models for high-quality tweet creation
- **Customizable Output**: Generate 1-10 tweets per request
- **Topic Flexibility**: Create tweets on any topic or theme
- **User-Friendly Interface**: Clean and intuitive Streamlit web interface
- **Real-time Generation**: Instant tweet generation with a single button click

## 🛠️ Technologies Used

- **Streamlit**: Web application framework
- **Google GenAI SDK**: Direct integration with Google's APIs
- **OpenAI SDK**: Direct integration with OpenAI's APIs
- **Google Gemini AI & OpenAI GPT**: Advanced language models for content generation
- **Python**: Core programming language

## 📋 Prerequisites

- Python 3.8 or higher
- Google AI API key (for Gemini)
- OpenAI API key (for OpenAI GPT)
- Streamlit account (for deployment with secrets)

## 🔧 Installation

1. **Clone the repository**:
   ```bash
   git clone <your-repository-url>
   cd tweet-generator
   ```

2. **Install required dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up API Keys**:
   - For Gemini: Get your API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
   - For OpenAI: Get your API key from [OpenAI Developer Platform](https://platform.openai.com/api-keys)
   - For local development, create a `.streamlit/secrets.toml` file:
     ```toml
     GOOGLE_API_KEY = "your-google-api-key-here"
     OPENAI_API_KEY = "your-openai-api-key-here"
     ```

## 🚀 Usage

### Local Development

Depending on the LLM model you want to use, run the respective file:

**To use Google Gemini:**
```bash
streamlit run main.py
```

**To use OpenAI GPT:**
```bash
streamlit run openai_main.py
```

2. **Open your browser** and navigate to `http://localhost:8501`

3. **Generate tweets**:
   - Enter your desired topic in the text input field
   - Select the number of tweets (1-10)
   - Click the "Generate" button
   - View your AI-generated tweets!

### Deployment

For Streamlit Cloud deployment:

1. Push your code to GitHub
2. Connect your repository to [Streamlit Cloud](https://streamlit.io/cloud)
3. Add your `GOOGLE_API_KEY` and `OPENAI_API_KEY` to the app's secrets in the Streamlit Cloud dashboard
4. Deploy your app (Specify `main.py` or `openai_main.py` as the entrypoint)

## 📁 Project Structure

```
tweet-generator/
│
├── main.py                # Main Streamlit application utilizing Google Gemini
├── openai_main.py         # Main Streamlit application utilizing OpenAI GPT
├── requirements.txt       # Python dependencies
├── .streamlit/
│   └── secrets.toml      # Local secrets (not committed)
└── README.md             # Project documentation
```

## 🔑 Environment Variables

| Variable | Description | Required |
|----------|-------------|-----------|
| `GOOGLE_API_KEY` | Your Google API key for Gemini execution | Yes (if using `main.py`) |
| `OPENAI_API_KEY` | Your OpenAI API key for OpenAI execution | Yes (if using `openai_main.py`) |

## 📝 Code Overview

### Key Components

1. **Prompt Template**: Structured template for generating tweets
   ```python
   tweet_template = "Give me {number} tweets on {topic}"
   ```

2. **Client Initialization**:
   - *Gemini*: `client = genai.Client(api_key=st.secrets['GOOGLE_API_KEY'])`
   - *OpenAI*: `client = OpenAI(api_key=st.secrets['OPENAI_API_KEY'])`

3. **Content Generation**: Generating output directly from the API
   - *Gemini*:
     ```python
     response = client.models.generate_content(
         model="gemini-2.5-flash",
         contents=prompt
     )
     ```
   - *OpenAI*:
     ```python
     response = client.chat.completions.create(
         model="gpt-4o-mini",
         messages=[{"role": "user", "content": prompt}]
     )
     ```

### User Interface

- **Header**: Application title and description
- **Topic Input**: Text field for entering tweet topics
- **Number Selection**: Numeric input for tweet quantity (1-10)
- **Generate Button**: Triggers AI tweet generation
- **Output Display**: Shows generated tweets

## 🎯 Use Cases

- **Social Media Managers**: Quickly generate tweet ideas for campaigns
- **Content Creators**: Get inspiration for social media posts
- **Marketers**: Create engaging promotional tweets
- **Individuals**: Generate personal tweets on various topics
- **Businesses**: Develop brand-consistent social media content

## 🔒 Security Notes

- Never commit your API keys to version control
- Use Streamlit secrets for secure key management
- Ensure your `.streamlit/secrets.toml` is in your `.gitignore`

## 🐛 Troubleshooting

### Common Issues

1. **API Key Error**:
   - Ensure your Google AI API key is correctly set in secrets
   - Verify the key has proper permissions

2. **Import Errors**:
   - Check that all required packages are installed
   - Verify Python version compatibility

3. **Model Access Issues**:
   - Ensure you have access to Gemini 2.5 Flash model
   - Check your Google AI quota and billing

## 📈 Future Enhancements

- [ ] Tweet sentiment analysis
- [ ] Hashtag suggestions
- [ ] Tweet scheduling integration
- [ ] Multiple AI model support
- [ ] Tweet templates and styles
- [ ] Export functionality (CSV, JSON)
- [ ] Tweet character count validation
- [ ] Batch processing capabilities

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Build Fast With AI**

## 🙏 Acknowledgments

- Google AI for providing the Gemini model and GenAI SDK
- OpenAI for providing the GPT model and OpenAI SDK
- Streamlit team for the amazing web framework

---

**Made with ❤️ using Streamlit, Google Gemini and OpenAI**
