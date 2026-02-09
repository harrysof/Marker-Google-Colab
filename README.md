[README.md](https://github.com/user-attachments/files/25171570/README.md)
# Marker PDF Converter - Google Colab Notebook

A ready-to-use Google Colab notebook for converting PDFs and other documents to Markdown using [Marker](https://github.com/VikParuchuri/marker).

## 🚀 Features

- **Multi-format support**: Convert PDFs, images, PPTX, DOCX, XLSX, HTML, and EPUB files to markdown, JSON, chunks, and HTML
- **Advanced formatting preservation**: Tables, forms, equations, inline math, links, and code blocks
- **Multi-language support**: Works with documents in all languages
- **Image extraction**: Automatically extracts and saves images from documents
- **GPU acceleration**: Optimized for GPU, but also works on CPU or MPS
- **LLM mode**: Optional integration with Gemini for highest accuracy
- **Table extraction**: Dedicated mode for extracting only tables
- **Batch processing**: Convert multiple files at once

## 📋 Prerequisites

- Google Colab account (free tier works)
- GPU runtime recommended (T4 or higher)
  - Go to **Runtime → Change runtime type** → Select **T4 GPU**

## 🎯 Quick Start

1. Open the notebook in Google Colab
2. Run the GPU check cell to verify GPU is enabled
3. Install Marker (takes ~2-3 minutes)
4. Upload your document
5. Run the conversion cell
6. Download your converted markdown file

## 📖 What's Inside

The notebook includes:

### 1. **Setup Section**
- GPU availability check
- Marker installation with full document support

### 2. **Basic Conversion**
- Simple file upload interface
- One-click conversion to markdown
- Results viewing and downloading

### 3. **Advanced Features**
- **LLM Integration**: Use Gemini API for enhanced accuracy
- **Custom converters**: Switch between different output formats
- **Table extraction**: Extract only tables from documents
- **Batch processing**: Convert multiple files simultaneously

### 4. **Output Options**
- View converted markdown directly in the notebook
- Download individual files or entire output folders
- Access extracted images

## 🔧 Common Use Cases

### Standard PDF to Markdown
```python
!marker_single "document.pdf" --output_dir ./output
```

### Extract Tables Only
```python
!marker_single "document.pdf" --output_dir ./output_tables --converter_cls marker.converters.table.TableConverter
```

### High-Accuracy Mode with LLM
```python
!marker_single "document.pdf" --use_llm --gemini_api_key "YOUR_API_KEY"
```

### Batch Convert Multiple Files
```python
!marker ./batch_input --output_dir ./batch_output --workers 4
```

## 🎨 Supported Input Formats

- PDF
- Images (PNG, JPG, JPEG, etc.)
- PowerPoint (PPTX)
- Word (DOCX)
- Excel (XLSX)
- HTML
- EPUB

## 💡 Tips & Best Practices

### For Better Accuracy
- Use `--use_llm` flag with a Gemini API key
- Use `--force_ocr` for documents with garbled text
- Use `--redo_inline_math` for highest quality math conversion

### Useful Flags
- `--page_range "0,5-10,20"` - Process specific pages only
- `--paginate_output` - Add page numbers to output
- `--disable_image_extraction` - Skip image extraction
- `--debug` - Enable debug mode for troubleshooting

### Memory Optimization
- Reduce worker count for large files
- Split very large PDFs into smaller chunks
- Use GPU runtime with more RAM if available

## 📊 Example Output

The notebook converts documents while preserving:
- ✅ Text formatting and structure
- ✅ Tables (with proper alignment)
- ✅ Mathematical equations
- ✅ Embedded images
- ✅ Links and references
- ✅ Code blocks
- ✅ Forms and structured data

## 🌍 Language Support

Marker supports documents in multiple languages. See the [full language list](https://github.com/VikParuchuri/surya/blob/master/surya/recognition/languages.py).

## 🔗 Resources

- **Marker GitHub**: https://github.com/VikParuchuri/marker
- **Documentation**: Check the Marker repository for detailed documentation
- **Issues**: Report problems on the Marker GitHub issues page

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs or issues
- Suggest new features
- Submit pull requests
- Share your use cases

## 📝 License

This notebook is provided as-is for educational and practical use. Marker is maintained by VikParuchuri - check the [official repository](https://github.com/VikParuchuri/marker) for license details.

## ⚠️ Troubleshooting

**GPU not available?**
- Make sure you've selected a GPU runtime in Colab settings
- Free tier has limited GPU access - try again later if unavailable

**Installation fails?**
- Restart the runtime and try again
- Check that you're using Python 3

**Conversion is slow?**
- Ensure GPU is enabled and active
- Reduce the number of workers
- Process smaller batches of pages

**Out of memory errors?**
- Use a smaller batch size
- Process fewer pages at once
- Switch to a runtime with more RAM

## 📧 Support

For issues specific to this notebook, open an issue in this repository. For Marker-related questions, refer to the [official Marker repository](https://github.com/VikParuchuri/marker).

---

**Made with ❤️ for easy document conversion**
