# Deepfake Detection using CNN and Streamlit

## Project Overview

This project aims to detect deepfake videos using a Convolutional Neural Network (CNN) model integrated with a Streamlit web application. The model analyzes frames from a video, detects faces, and classifies them as either real or deepfake. The computational power of Google Colab is leveraged for model inference, while a user-friendly interface is provided through Streamlit.

## Requirements

- Python 3.7+
    - Numpy 
    - Scikit
- TensorFlow 2.x
- OpenCV
- MTCNN (Multi-Task Cascaded Convolutional Neural Networks)
- Flask
- Streamlit
- ngrok

## Setup Instructions

1. **Clone the Repository**

    ```bash
    git clone https://github.com/yourusername/deepfake-detection.git
    cd deepfake-detection
    ```

2. **Install Dependencies**

    ```bash
    pip install -r requirements.txt
    ```

3. **Set Up Google Colab**

    - Open the provided Jupyter Notebook `DeepfakeDetection_Finale.ipynb` in Google Colab.
    - Ensure that the notebook is connected to a GPU T4 runtime.
    - Install the necessary libraries within the Colab environment.
    - Run the notebook to load the model and start the Flask server.

4. **Expose Colab Environment with ngrok**

    - Install ngrok in Colab:

        ```python
        !pip install flask-ngrok
        from flask_ngrok import run_with_ngrok
        ```

    - Start the Flask app with ngrok:

        ```python
        run_with_ngrok(app)
        if __name__ == '__main__':
            app.run()
        ```

    - Copy the public URL provided by ngrok.

5. **Update Streamlit App**

    - Open `deepfakeDetection.py`.
    - Update the `colab_url` variable with the ngrok URL from Colab.

## Running the Project

1. **Run the Colab Notebook**

    - Execute all cells in the `DeepfakeDetection_Finale.ipynb` notebook to start the Flask server.

2. **Run the Streamlit Application Locally**

    ```bash
    streamlit run app.py
    ```

## Using the Streamlit Application

1. **Upload Video**

    - Use the file uploader in the Streamlit app to upload a video file in mp4, mov, avi, or mkv format.

2. **View Results**

    - The app will process the video, detect faces, and classify the video as either real or deepfake. The result will be displayed on the webpage.

## Explanation of the Code

### Jupyter Notebook (`DeepfakeDetection_Finale.ipynb`)

- **Model Loading and Preprocessing**: The notebook loads the pre-trained CNN model and defines functions for image preprocessing and prediction.
- **Flask Server**: A Flask server is set up to expose an endpoint for predicting deepfake videos.

### Streamlit Application (`deepfakeDetection.py`)

- **File Upload**: Users can upload video files through the Streamlit interface.
- **Video Processing**: The uploaded video is sent to the Colab environment for processing using the Flask API.
- **Result Display**: The prediction result is retrieved from the Colab environment and displayed to the user.

## Contributing

We welcome contributions! Please read our [Contributing Guidelines](CONTRIBUTING.md) for more details.


## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

