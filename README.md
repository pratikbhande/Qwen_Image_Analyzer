# Image Analyzer with Voice Assistant

This project is an interactive application that combines visual and voice-based AI capabilities to analyze images and respond to user queries through both text and audio. The application utilizes advanced AI models from the `Qwen` series and other tools to deliver an enriched multimedia user experience.

## Features

- **Image Analysis**: Upload an image and ask questions about its content.
- **Voice Query Support**: Record your query as audio, and the app will transcribe it into text for analysis.
- **Text-to-Speech Response**: The AI generates a response and provides it in both text and audio formats.
- **Multimodal AI**: Powered by the `Qwen2-VL-2B-Instruct` model for visual and textual data understanding.

## Prerequisites

Ensure you have the following dependencies installed:

- Python 3.8+
- [Gradio](https://gradio.app/) for building the user interface
- [Transformers](https://huggingface.co/transformers/) library by Hugging Face
- [SpeechRecognition](https://pypi.org/project/SpeechRecognition/) for audio transcription
- [gTTS](https://pypi.org/project/gTTS/) for text-to-speech conversion
- [Pillow](https://pypi.org/project/Pillow/) for image processing
- PyTorch with CUDA support for GPU acceleration

## Installation

1. Clone this repository:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Ensure that you have the `Qwen2-VL-2B-Instruct` model and processor available. You can download them from the Hugging Face repository.

## Usage

1. Run the application:
   ```bash
   python app.py
   ```

2. Open the provided local or public URL in your browser.

3. Interact with the app by:
   - Uploading an image.
   - Entering a query in the text box or recording your query as audio.

4. Click the **Analyze** button to receive a response. The analysis result will be displayed as text and an audio file will be generated for playback.

## File Structure

- **`app.py`**: Main application file containing the code for the Gradio interface and backend logic.
- **`requirements.txt`**: List of dependencies required for the project.
- **`output_audio.mp3`**: Temporary file generated for the audio response (overwritten each time).

## How It Works

1. **Audio Processing**:
   - If a voice query is provided, the `speech_recognition` library transcribes the audio into text.
   - If no voice input is given, the query is read directly from the text box.

2. **Image and Query Analysis**:
   - The uploaded image is processed using the `Pillow` library.
   - Queries are formatted into a chat-like structure using the `AutoProcessor`.
   - The `Qwen2-VL-2B-Instruct` model processes the image and query to generate a response.

3. **Text-to-Speech Conversion**:
   - The generated text response is converted into an audio file using `gTTS`.

4. **Output Delivery**:
   - The app displays the text response and provides an audio playback option.

## Dependencies

- Gradio
- Transformers
- SpeechRecognition
- gTTS
- PyTorch
- Pillow

## Notes

- Ensure GPU support for efficient model execution.
- The `output_audio.mp3` file is overwritten with each new query to conserve storage.

## Future Enhancements

- Support for multilingual queries and responses.
- Advanced image annotation features.
- Improved audio quality for text-to-speech outputs.


## Acknowledgments

- [Hugging Face](https://huggingface.co/) for providing pre-trained models and processors.
- The contributors and maintainers of `Gradio`, `SpeechRecognition`, and `gTTS` for their open-source libraries.

