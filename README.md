# 3D Blob Generator

An interactive 3D blob generator built with Three.js featuring real-time material controls, advanced noise systems, dynamic lighting, and post-processing effects.

![3D Blob Generator](https://img.shields.io/badge/Three.js-r128-green) ![License](https://img.shields.io/badge/license-MIT-blue)

## Features

- **Real-time Material Controls**: Adjust metalness, roughness, clearcoat, and IOR for physically-based rendering
- **Advanced Noise System**: Multiple octave noise with configurable frequency, waves, and angular displacement
- **Dynamic Lighting**: Three-light setup with customizable intensities and colors
- **Interactive Controls**: Mouse-controlled rotation with smooth interpolation
- **Post-Processing**: Bloom effects and exposure control
- **Responsive Design**: Collapsible control panels with organized sections

## Usage

### Quick Start
1. Open `index.html` in a web browser
2. Use the control panels on the right to adjust blob properties
3. Click and drag to rotate the blob
4. Experiment with different settings to create unique blob shapes

### Local Development
```bash
# Serve with Python (recommended for local development)
python -m http.server 8000

# Or with Node.js
npx http-server

# Then visit http://localhost:8000
```

## Controls

### Blob Material
- **Colors**: Three-color gradient system (Cyan, Purple, White)
- **Metalness**: Controls metallic appearance (0-1)
- **Roughness**: Surface roughness for reflections (0-1)
- **Clearcoat**: Clear coating layer intensity (0-1)
- **IOR**: Index of refraction for realistic glass/water effects (1-3)

### Blob Noise
- **Frequency**: Base noise frequency for surface deformation
- **Num Waves**: Number of wave bands in the noise pattern
- **Surface Distort**: Overall distortion intensity
- **Surface Frequency**: Detail noise frequency
- **Speed**: Animation speed
- **Decay**: Amplitude decay between octaves
- **Angles 1-3**: Rotational offsets for noise layers

### Blob Geometry
- **Scale**: Overall size of the blob
- **Rotation Speed**: Auto-rotation speed when not interacting

### Lighting
- **Ambient**: Global ambient light intensity
- **Env Map**: Environment map reflection intensity
- **Light 1-3**: Individual directional light intensities

### Post-Processing
- **Bloom Strength**: Intensity of the bloom effect
- **Bloom Threshold**: Brightness threshold for bloom
- **Exposure**: Overall scene exposure

## Technical Details

### Built With
- **Three.js r128**: 3D graphics library
- **WebGL**: Hardware-accelerated rendering
- **GLSL Shaders**: Custom vertex and fragment shaders for noise generation

### Shader Features
- Multi-octave banded noise generation
- Angular noise rotation
- Physically-based material properties
- Gradient color mapping
- Real-time displacement

### Browser Support
- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

Requires WebGL support and modern JavaScript features.

## Development

### Project Structure
```
blob-mixer/
├── index.html          # Main application file
├── README.md           # This file
├── package.json        # NPM configuration
├── .gitignore         # Git ignore rules
└── LICENSE            # MIT license
```

### Customization
The blob generator is highly customizable. Key areas for modification:

1. **Noise Functions**: Edit the GLSL shader code in the `material.onBeforeCompile` function
2. **UI Controls**: Add new control groups in the HTML and corresponding JavaScript
3. **Material Properties**: Extend the `params` object and update functions
4. **Lighting Setup**: Modify the light creation and positioning code

### Performance Considerations
- Uses 64x64 sphere geometry for good balance of quality and performance
- Shader compilation happens once at startup
- Real-time parameter updates are optimized with RAF
- Error handling prevents crashes on unsupported devices

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Inspiration

Inspired by the amazing blob generators and Three.js community. Special thanks to the Three.js team for creating such a powerful and accessible 3D library.

## Links

- [Three.js Documentation](https://threejs.org/docs/)
- [WebGL Fundamentals](https://webglfundamentals.org/)
- [Shader Reference](https://www.khronos.org/opengl/wiki/OpenGL_Shading_Language)
