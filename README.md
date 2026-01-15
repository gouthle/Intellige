# INTELLIGE

**Real-time Audio Translation App for macOS**

INTELLIGE is a sleek, modern macOS application that provides real-time speech recognition and translation between 12 languages. Speak in one language and instantly see and hear the translation in another.

![Version](https://img.shields.io/badge/version-0.1%20beta-blue)
![Platform](https://img.shields.io/badge/platform-macOS-lightgrey)
![Swift](https://img.shields.io/badge/Swift-5.0-orange)
![License](https://img.shields.io/badge/license-MIT-green)

## ✨ Features

- **Real-time Speech Recognition** - Continuous speech-to-text using Apple's Speech framework
- **Instant Translation** - Powered by Groq API with LLaMA 3.3 70B model
- **12 Supported Languages** - English, Russian, Spanish, French, German, Italian, Portuguese, Polish, Ukrainian, Japanese, Chinese, Korean
- **Beautiful UI** - Modern dark interface with animated 3D globe and particle effects
- **Audio Output** - Text-to-speech for translations (coming soon)
- **Responsive Design** - Adapts to different window sizes

## 🎯 Requirements

- macOS 13.0 or later
- Microphone access
- Internet connection for translation
- Groq API key (free tier available)

## 🚀 Getting Started

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/intellige.git
cd intellige
```

2. Open the project in Xcode:
```bash
open INTELLIGE.xcodeproj
```

3. Add your Groq API key:
   - Get a free API key from [Groq Console](https://console.groq.com)
   - Replace the placeholder in `AudioManager.swift`:
   ```swift
   private let groqAPIKey = "your_api_key_here"
   ```

4. Build and run the project in Xcode (⌘R)

### First Launch

1. Grant microphone permissions when prompted
2. Select your source language (the language you'll speak)
3. Select your target language (translation output)
4. Click the animated globe to start recording
5. Speak naturally - translation appears in real-time

## 🎮 Usage

### Language Selection

- **Source Language**: Click the "FROM" button to select the language you'll speak
- **Target Language**: Click the "TO" button or tap it multiple times to cycle through languages

### Recording

- Click the central globe button to start/stop recording
- The globe turns red and expands when actively recording
- Status indicator shows current state (Ready/Recording)

### Translation Flow

1. Speak into your microphone
2. See transcribed text in the "Original" box
3. Translation appears automatically in the "Translation" box after 1.5 seconds of silence
4. Audio playback of translation (feature in development)

## 🛠️ Technical Details

### Architecture

- **SwiftUI** - Modern declarative UI framework
- **Speech Framework** - Native speech recognition
- **AVFoundation** - Audio engine and synthesis
- **Combine** - Reactive programming

### Translation API

The app uses Groq's ultra-fast inference API with the LLaMA 3.3 70B Versatile model:
- Average latency: < 1 second
- High accuracy across multiple languages
- Cost-effective with generous free tier

### Performance Optimizations

- Debounced translation (1.5s delay) to avoid excessive API calls
- Optimized particle system with Canvas rendering
- Efficient audio buffer handling
- Minimal UI re-renders with proper state management

## 🎨 UI Components

- **FallingParticlesView** - Ambient animated background
- **InteractiveGlobeButton** - 3D rotating globe with 600+ particles
- **LanguageSelectorView** - Modal language picker
- **Responsive Layout** - GeometryReader-based scaling

## 📋 Supported Languages

| Language | Code | Speech Code |
|----------|------|-------------|
| English | en | en-US |
| Russian | ru | ru-RU |
| Spanish | es | es-ES |
| French | fr | fr-FR |
| German | de | de-DE |
| Italian | it | it-IT |
| Portuguese | pt | pt-PT |
| Polish | pl | pl-PL |
| Ukrainian | uk | uk-UA |
| Japanese | ja | ja-JP |
| Chinese | zh | zh-CN |
| Korean | ko | ko-KR |

## 🔧 Configuration

### API Settings

Modify translation behavior in `AudioManager.swift`:
```swift
let requestBody: [String: Any] = [
    "model": "llama-3.3-70b-versatile",
    "temperature": 0.3,  // Adjust for creativity (0.0-1.0)
    "max_tokens": 1000   // Maximum translation length
]
```

### UI Customization

Colors and styles can be adjusted in `ContentView.swift`:
- Background gradient colors
- Particle density and speed
- Globe size and rotation speed
- Text sizes and spacing

## 🐛 Known Issues

- Text-to-speech audio playback is disabled to prevent conflicts with recording
- Translation may occasionally include formatting preamble
- Microphone tap removal during speech synthesis needs refinement

## 🗺️ Roadmap

- [ ] Fix audio playback during recording
- [ ] Add conversation history
- [ ] Support for offline translation
- [ ] Custom voice selection for TTS
- [ ] Export translations
- [ ] Multiple translation engine support
- [ ] iOS/iPadOS companion app

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Groq](https://groq.com) for providing fast inference API
- Apple Speech Framework for speech recognition
- SwiftUI community for design inspiration

## 📧 Contact

@GOUTLS (gouthle)
www.instagram.com/gouthle

Project Link: [https://github.com/yourusername/intellige](https://github.com/yourusername/intellige)](https://github.com/gouthle/Intellige-REALTIME)

---

**Note**: This is a beta version (0.1). Please report any bugs or feature requests in the Issues section.
