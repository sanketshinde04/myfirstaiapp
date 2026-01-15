# Tweet Generator 

A powerful AI-powered tweet generation application built with Streamlit and Google's Gemini AI model. Generate engaging tweets on any topic with just a few clicks!

## 🚀 Features

- **AI-Powered Generation**: Uses Google's Gemini 2.5 Flash model for high-quality tweet creation
- **Customizable Output**: Generate 1-10 tweets per request
- **Topic Flexibility**: Create tweets on any topic or theme
- **User-Friendly Interface**: Clean and intuitive Streamlit web interface
- **Real-time Generation**: Instant tweet generation with a single button click

## 🛠️ Technologies Used

- **Streamlit**: Web application framework
- **LangChain**: LLM orchestration and chaining
- **Google Gemini AI**: Advanced language model for content generation
- **Python**: Core programming language

## 📋 Prerequisites

- Python 3.8 or higher
- Google AI API key
- Streamlit account (for deployment with secrets)

## 🔧 Installation

1. **Clone the repository**:
   ```bash
   git clone <your-repository-url>
   cd tweet-generator
   ```

2. **Install required dependencies**:
   ```bash
   pip install streamlit langchain-google-genai langchain-classic langchain-core
   ```

3. **Set up Google AI API Key**:
   - Get your API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
   - For local development, create a `.streamlit/secrets.toml` file:
     ```toml
     GOOGLE_API_KEY = "your-google-api-key-here"
     ```

## 🚀 Usage

### Local Development

1. **Run the application**:
   ```bash
   streamlit run app.py
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
3. Add your `GOOGLE_API_KEY` to the app's secrets in the Streamlit Cloud dashboard
4. Deploy your app

## 📁 Project Structure

```
tweet-generator/
│
├── app.py                 # Main Streamlit application
├── requirements.txt       # Python dependencies
├── .streamlit/
│   └── secrets.toml      # Local secrets (not committed)
└── README.md             # Project documentation
```

## 🔑 Environment Variables

| Variable | Description | Required |
|----------|-------------|-----------|
| `GOOGLE_API_KEY` | Your Google AI API key | Yes |

## 📝 Code Overview

### Key Components

1. **Prompt Template**: Structured template for generating tweets
   ```python
   tweet_template = "Give me {number} tweets on {topic}"
   ```

2. **Gemini Model**: Google's advanced language model
   ```python
   gemini_model = ChatGoogleGenerativeAI(model="gemini-2.5-flash")
   ```

3. **LangChain Integration**: Seamless chaining of prompt and model
   ```python
   tweet_chain = tweet_prompt | gemini_model
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

- Google AI for providing the Gemini model
- Streamlit team for the amazing web framework
- LangChain community for the excellent LLM orchestration tools

---

**Made with ❤️ using Streamlit and Google Gemini AI**
