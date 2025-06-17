# 3D Blob Generator

An interactive 3D blob generator built with Three.js featuring real-time material controls, advanced noise systems, dynamic lighting, post-processing effects, and a comprehensive preset management system.

![3D Blob Generator](https://img.shields.io/badge/Three.js-r128-green) ![License](https://img.shields.io/badge/license-MIT-blue) ![Presets](https://img.shields.io/badge/presets-exportable-orange)

## ✨ Features

### 🎨 **Real-time Material Controls**
- **Physically-Based Rendering** with metalness, roughness, clearcoat, and IOR
- **Dynamic color gradients** with three-color mixing system
- **Subsurface scattering** for translucent effects
- **Environmental reflections** with multiple HDR styles

### 🌊 **Advanced Noise System**
- **Multiple noise types**: Banded, Worley/Voronoi, Curl Noise, FBM, Mixed Complex
- **Multi-octave displacement** with configurable frequency and amplitude
- **Angular rotation controls** for unique surface patterns
- **Domain warping** for complex distortions
- **Surface pole control** for natural deformation

### 💡 **Dynamic Lighting**
- **5-light setup** with individual intensity and distance controls
- **PointLight system** with realistic falloff and shadows
- **Color-matched lighting** that follows gradient colors
- **Penumbra controls** for soft shadow edges

### 🎮 **Interactive Controls**
- **Voice assistant-style UI** with glassmorphism design
- **Mouse-controlled rotation** with smooth interpolation
- **Play/pause animation** with visual feedback
- **Collapsible control panels** for clean viewing

### 🎯 **Preset Management**
- **Built-in presets**: Purple Rain, Iridescent, Pink Floyd
- **Save custom presets** with user-defined names
- **Export/Import system** for sharing configurations
- **Session persistence** with JSON file support

### ⚡ **Post-Processing**
- **Bloom effects** with adjustable strength and threshold
- **Exposure control** for HDR-like appearance
- **Multiple environment styles** (Studio, Sunset, Cosmic, Minimal)

## 🚀 Quick Start

### **Option 1: Direct Use**
1. Open `index.html` in a modern web browser
2. Click the **⚙** button to open controls
3. Experiment with the presets in the dropdown
4. Adjust parameters in real-time

### **Option 2: Local Development**
```bash
# Clone the repository
git clone https://github.com/yourusername/blob-mixer.git
cd blob-mixer

# Serve locally (recommended)
python -m http.server 8000
# or
npx http-server -p 8000

# Visit http://localhost:8000
```

## 🎛 Controls Guide

### **Bottom Panel (Voice Assistant Style)**
- **× (Close)** - Reset camera view to default position
- **🎙 (Microphone)** - Toggle animation play/pause
- **⚙ (Settings)** - Open/close the control panels

### **Control Panels**
#### **Presets**
- **Choose from built-in presets** or create custom ones
- **Save current settings** with custom names
- **Export/Import** preset collections as JSON files

#### **Blob Material**
- **Colors**: Three-color gradient system
- **Material Properties**: Metalness, roughness, clearcoat, IOR
- **Subsurface Effects**: Scattering intensity and color

#### **Blob Noise**
- **Noise Type**: Switch between different algorithms
- **Surface Controls**: Distortion, frequency, wave count
- **Animation**: Speed, decay, angular offsets

#### **Environment & Lighting**
- **Environment Styles**: Studio, Sunset, Cosmic, Minimal
- **5-Light System**: Individual intensity and distance controls
- **Ambient & Reflection**: Global lighting settings

#### **Post-Processing**
- **Bloom**: Strength and threshold for glow effects
- **Exposure**: HDR-style brightness control

## 🎨 Preset Gallery

### **Purple Rain** (Default)
- Dark purple cosmic background
- Cyan-to-purple-to-white gradient
- Metallic surface with strong reflections
- Classic horizontal banding pattern

### **Iridescent**
- Light blue-cyan background
- Blue-to-yellow-to-purple gradient
- Glass-like transparency effects
- High surface distortion for dramatic ridges

### **Pink Floyd**
- Pink cosmic background
- Yellow-to-purple gradient
- Non-metallic matte surface
- High ambient lighting with fine detail

## 💾 Preset Management

### **Creating Custom Presets**
1. Adjust all parameters to your liking
2. Enter a name in the "Save Current Settings" field
3. Click **Save** - your preset is added to the dropdown

### **Sharing Presets**
1. Click **"Export All Presets"** to download a JSON file
2. Share the file with others
3. Others can **"Import Presets"** to add your creations

### **Preset File Format**
```json
{
  "version": "1.0",
  "timestamp": "2024-01-01T00:00:00.000Z",
  "presets": {
    "your-preset-name": {
      "ambient": 0,
      "frequency": 3.05,
      "color1": {"r": 0, "g": 1, "b": 0.97},
      // ... all parameters
    }
  }
}
```

## 🛠 Technical Details

### **Built With**
- **Three.js r128** - 3D graphics library
- **WebGL** - Hardware-accelerated rendering
- **GLSL Shaders** - Custom vertex and fragment shaders

### **Shader Features**
- **Multi-octave noise generation** with 5 different algorithms
- **Physically-based material properties**
- **Real-time displacement mapping**
- **Gradient color interpolation**
- **Domain warping and pole control**

### **Performance Optimizations**
- **512 segments** geometry for high detail
- **Efficient shader compilation** and uniform updates
- **Optimized render loop** with RAF
- **Memory management** for environment textures

### **Browser Support**
- **Chrome 60+** ✅
- **Firefox 55+** ✅  
- **Safari 12+** ✅
- **Edge 79+** ✅

*Requires WebGL support and modern JavaScript features*

## 📁 Project Structure

```
blob-mixer/
├── index.html          # Main application
├── README.md           # This documentation
├── package.json        # NPM configuration
├── .gitignore         # Git ignore rules
└── LICENSE            # MIT license
```

## 🚀 Advanced Usage

### **URL Parameters**
The blob generator supports URL parameters matching the original BlobMixer format:
```
?ambient=0&frequency=3.05&metalness=1&color1=rgba(0,255,248,1)
```

### **Keyboard Shortcuts**
- **Spacebar** - Toggle animation
- **R** - Reset view
- **S** - Toggle settings panel

### **Custom Modifications**

#### **Adding New Noise Types**
Extend the noise functions in the vertex shader:
```glsl
// Add your custom noise function
float customNoise(vec3 p) {
    // Your implementation here
    return value;
}
```

#### **Creating New Presets**
Add to the `presets` object in JavaScript:
```javascript
presets['my-preset'] = {
    ambient: 0.5,
    frequency: 4.0,
    // ... your parameters
};
```

## 🤝 Contributing

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

### **Development Guidelines**
- Test in multiple browsers
- Maintain 60fps performance
- Follow existing code style
- Update documentation for new features

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Three.js Community** for the amazing 3D library
- **14islands** for the original BlobMixer inspiration
- **Microsoft Fluent Design** for UI component inspiration
- **WebGL Fundamentals** for shader programming resources

## 🔗 Links

- [Three.js Documentation](https://threejs.org/docs/)
- [WebGL Fundamentals](https://webglfundamentals.org/)
- [GLSL Shader Reference](https://www.khronos.org/opengl/wiki/OpenGL_Shading_Language)
- [Original BlobMixer](https://blobmixer.14islands.com/)

---

**Made with ❤️ and WebGL**
