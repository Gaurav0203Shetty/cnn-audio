# Audio CNN Visualisation

This project provides a complete pipeline for training a Convolutional Neural Network (CNN) on audio data and visualizing its internal feature maps and spectrograms through a modern web interface built with Next.js and TypeScript.

## Features

- **Audio Classification with CNN**: Train a CNN model on audio files for tasks such as sound event detection or classification.
- **Feature Map Visualization**: Inspect internal CNN feature maps layer-by-layer using a color-coded grid.
- **Spectrogram Display**: Visualize audio spectrograms for input samples.
- **Modern Web UI**: Interactive, responsive frontend built with Next.js, React, and Tailwind CSS.
- **TensorBoard Integration**: Monitor training progress and metrics with TensorBoard logs.

## Project Structure

```
.
├── 1.wav, chirpingbirds.wav         # Example audio files
├── main.py                         # Main script (entry point)
├── model.py                        # CNN model definition
├── train.py                        # Training script
├── requirements.txt                # Python dependencies
├── tensorboard_logs/               # TensorBoard event logs
└── audio-cnn-visualisation/        # Frontend (Next.js app)
    ├── src/
    │   ├── app/                    # Next.js pages and layouts
    │   ├── components/             # React components (FeatureMap, Waveform, etc.)
    │   ├── lib/                    # Utility functions and color mapping
    │   └── styles/                 # Global styles
    ├── public/                     # Static assets
    ├── package.json                # Frontend dependencies
    └── ...
```

## Getting Started

### 1. Backend: Model Training & Feature Extraction

#### Install Python Dependencies
```bash
pip install -r requirements.txt
```

#### Train the Model
```bash
python train.py
```
- This will train the CNN on your audio data and save model weights and TensorBoard logs in `tensorboard_logs/`.

#### Run the Main Script
```bash
python main.py
```
- This script may be used for inference, feature extraction, or serving data to the frontend (customize as needed).

### 2. Frontend: Visualization App

#### Install Node.js Dependencies
```bash
cd audio-cnn-visualisation
npm install
```

#### Start the Development Server
```bash
npm run dev
```
- The app will be available at `http://localhost:3000`.

#### Build for Production
```bash
npm run build
npm start
```

## Key Components

- **FeatureMap.tsx**: Renders a 2D color-coded grid for CNN feature maps. Normalizes values and maps them to RGB using a custom color scale.
- **Waveform.tsx**: Displays the audio waveform.
- **ColorScale.tsx**: Shows the color mapping used for feature map visualization.
- **model.py**: Defines the CNN architecture for audio data.
- **train.py**: Handles data loading, training loop, and logging.

## Customization
- Add your own audio files in the root directory or update data loading logic in `train.py`.
- Adjust CNN layers in `model.py` for your specific task.
- Extend the frontend to visualize additional model internals or metrics.

## Requirements

- **Backend**: Python 3.8+, PyTorch or TensorFlow (as specified in `requirements.txt`), numpy, librosa, etc.
- **Frontend**: Node.js 18+, npm, Next.js, React, Tailwind CSS.

## TensorBoard
To monitor training:
```bash
tensorboard --logdir tensorboard_logs/
```

## Acknowledgements
- Inspired by open-source audio classification and visualization projects.
- Built with Next.js, React, and Tailwind CSS.
