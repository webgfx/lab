# WebGPU Memory Allocation Web Application

This is a complete standalone web application that allows you to allocate GPU memory using the WebGPU API. The application provides a simple interface with a dedicated button for 200MB memory allocation and includes comprehensive buffer verification.

## 📁 Files Overview

- **`webgpu-memory-allocation.html`** - Complete standalone HTML application with embedded CSS and JavaScript
- **`README.md`** - This documentation file

## 🚀 Features

### Core Functionality
- **200MB Memory Allocation**: Dedicated button for allocating 200MB of GPU memory
- **Real-time Monitoring**: Track total allocated memory, buffer count, and allocation status
- **Buffer Verification**: Each allocated buffer is tested with write/read operations to verify integrity
- **Performance Metrics**: Monitor allocation times and success rates
- **Device Information**: Display WebGPU device limits and capabilities
- **Buffer Tracking**: Individual buffer tracking with creation timestamps and verification status

### Technical Features
- **Pure Web Solution**: No Node.js dependencies - runs entirely in the browser
- **WebGPU Integration**: Uses modern WebGPU API for GPU memory allocation
- **Error Handling**: Graceful handling of allocation failures and device limits
- **Cross-browser Support**: Works in Chrome 113+, Edge 113+, and Firefox (experimental)
- **Standalone HTML**: Everything embedded in a single HTML file for easy deployment

## 🖥️ Running the Application

### Simple Setup (Recommended)
1. **Double-click** `webgpu-memory-allocation.html` to open it directly in your browser
2. **Or drag and drop** the HTML file into your browser window
3. Click the "Allocate 200MB" button to allocate GPU memory
4. Monitor memory usage and buffer details in real-time

### Using a Local Web Server (Alternative)
If you prefer to serve the file through a web server:

```bash
# Option 1: Using Python (if installed)
python -m http.server 8080

# Option 2: Using Node.js http-server (if installed)
npx http-server -p 8080

# Option 3: Using any other web server of your choice
```

Then open `http://localhost:8080/webgpu-memory-allocation.html` in your browser.

## ⚡ Quick Start

1. **Open** the `webgpu-memory-allocation.html` file in a WebGPU-compatible browser
2. **Check** that WebGPU is supported (you'll see device information displayed)
3. **Click** "Allocate 200MB" to create a GPU buffer
4. **Watch** the memory counter increase and new buffer entries appear
5. **Check** the browser console (F12) for detailed allocation and verification logs

## 🌐 Browser Requirements

### Supported Browsers
- **Chrome 113+**: Full WebGPU support
- **Edge 113+**: Full WebGPU support
- **Firefox**: Experimental support (enable `dom.webgpu.enabled` in `about:config`)
- **Safari**: Experimental support in Safari Technology Preview

### Enabling WebGPU
If WebGPU is not available:
1. Update to the latest browser version
2. Enable experimental features in browser flags
3. Ensure your GPU drivers are up to date

## 📊 Usage Examples

### Web Interface Usage
1. **Allocate 200MB**: Click the "Allocate 200MB" button to create a GPU buffer
2. **Monitor**: Watch the real-time memory statistics and buffer list
3. **Verification**: Each buffer is automatically tested with write/read operations
4. **Console Logs**: Check browser console (F12) for detailed allocation information

// Get memory information
const memoryInfo = allocator.getMemoryInfo();
console.log(`Total allocated: ${memoryInfo.totalAllocatedMB} MB`);
```

## 🎮 CLI Commands

When using the command-line interface:

```
alloc <size_mb> [count]   - Allocate buffer(s) (default: 10MB, 1 buffer)
clear <buffer_id|all>     - Clear specific buffer or all buffers
status                    - Show memory status and buffer list
info                      - Show device information
performance               - Show performance metrics
stress <count> <size_mb>  - Run stress test (default: 50 buffers, 10MB)
auto <interval> <size>    - Start auto allocation (default: 1000ms, 10MB)
stop                      - Stop auto allocation
help                      - Show help
exit/quit                 - Exit the program
## 🔧 Application Configuration

### Default Settings
- **Memory Allocation Size**: 200MB per buffer
- **Maximum Buffers**: Unlimited (limited by WebGPU device capabilities)
- **Buffer Usage Flags**: `STORAGE | COPY_DST | COPY_SRC`
- **Verification**: Each buffer is tested with write/read operations

### WebGPU Buffer Configuration
The application creates WebGPU buffers with the following properties:
```javascript
// Buffer creation for 200MB
const buffer = device.createBuffer({
    size: 200 * 1024 * 1024, // 200MB in bytes
    usage: GPUBufferUsage.STORAGE | GPUBufferUsage.COPY_DST | GPUBufferUsage.COPY_SRC,
    label: `Buffer_${bufferNumber}_200MB`
});
```

## 📈 Performance Monitoring

The application tracks several performance metrics:

- **Allocation Time**: Time taken for each buffer allocation
- **Success Rate**: Percentage of successful allocations
- **Memory Pressure Events**: System memory pressure occurrences
- **Total Allocated Memory**: Sum of all allocated buffer memory
- **Average Buffer Size**: Mean size of allocated buffers

## ⚠️ Important Notes

### Memory Limits
- WebGPU devices have hardware-specific memory limits
- The application will fail gracefully when limits are exceeded
- Use the device info display to check maximum buffer sizes

### Performance Considerations
- Large buffer allocations may cause temporary browser slowdown
- Monitor system memory usage when allocating multiple buffers
- Check browser console for detailed allocation and verification logs

### Browser Security
- WebGPU has built-in security restrictions
- Some allocations may fail due to browser limits
- Files should be served over HTTP/HTTPS for full WebGPU functionality

## 🛠️ Troubleshooting

### WebGPU Not Available
1. Ensure you're using a supported browser version (Chrome 113+, Edge 113+)
2. Update GPU drivers to the latest version
3. Enable WebGPU in browser experimental features if needed
4. Check if your GPU supports WebGPU

### Allocation Failures
1. Check browser console (F12) for detailed error messages
2. Verify you haven't exceeded device memory limits
3. Close other memory-intensive applications
4. Try refreshing the page to reset WebGPU state

### Performance Issues
1. Close other tabs or applications using GPU resources
2. Clear buffers by refreshing the page
3. Monitor system resource usage in Task Manager

## 📝 Application Features

The WebGPU Memory Allocation application provides:

- **Simple Interface**: Single button for 200MB memory allocation
- **Real-time Monitoring**: Track allocated memory and buffer count
- **Buffer Verification**: Each buffer is tested with write/read operations to ensure integrity
- **Detailed Logging**: Console output shows allocation progress and verification results
- **Device Information**: View WebGPU device capabilities and limits
- **Newest First**: Most recently allocated buffers appear at the top of the list

## 🎯 Use Cases

This application is useful for:

- **WebGPU Learning**: Understand how WebGPU memory allocation works
- **Performance Testing**: Measure GPU memory allocation performance on your hardware
- **Memory Limit Testing**: Discover your device's WebGPU memory limits
- **Development**: Test memory allocation patterns for WebGPU applications
- **Hardware Evaluation**: Compare WebGPU performance across different devices

## 📄 License

This project is open source and available under the MIT License.

---

**Happy Testing!** 🎉 Use this application to explore WebGPU memory allocation with specific buffer sizes.
