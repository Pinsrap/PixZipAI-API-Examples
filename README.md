# PixZipAI API Examples

Official code examples for integrating with the PixZipAI image compression API.

## 🚀 Getting Started

1. Sign up for a free account at [PixZipAI](https://pixzipai.io)
2. Get your API key from the [Dashboard](https://pixzipai.io/dashboard)
3. Choose your language below and start compressing!

## 📚 Examples

### PHP
- [Basic compression](examples/php/basic-compression.php)
- [Batch processing](examples/php/batch-processing.php)
- [Error handling](examples/php/error-handling.php)
- [Laravel integration](examples/php/laravel-example.php)

### Python
- [Basic compression](examples/python/basic_compression.py)
- [Async processing](examples/python/async_processing.py)
- [Django integration](examples/python/django_example.py)

### Node.js
- [Basic compression](examples/nodejs/basic-compression.js)
- [Express middleware](examples/nodejs/express-middleware.js)
- [Async/await example](examples/nodejs/async-await.js)

### cURL
- [Command line examples](examples/curl/examples.sh)

## 📖 API Documentation

Full API documentation is available at [https://pixzipai.io/api/docs](https://pixzipai.io/api/docs)

## 🔑 Authentication

All API requests require authentication using your API key:

```bash
Authorization: Bearer YOUR_API_KEY
```

## 📝 Quick Example

```php
<?php
$apiKey = 'YOUR_API_KEY';
$imageData = base64_encode(file_get_contents('image.jpg'));

$ch = curl_init('https://pixzipai.io/api/v1/compress');
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'Authorization: Bearer ' . $apiKey,
    'Content-Type: application/json'
]);
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode([
    'image' => $imageData,
    'format' => 'webp',
    'quality' => 85
]));

$response = curl_exec($ch);
$result = json_decode($response, true);

echo "Job ID: " . $result['job_id'];
```

## 🔄 API Workflow

1. **Upload** - Send your image as base64 encoded data
2. **Process** - Our AI analyzes and compresses your image
3. **Download** - Get your optimized image via the download URL

## 📊 Supported Formats

- **Input**: JPEG, PNG, WebP, AVIF
- **Output**: JPEG, PNG, WebP, AVIF
- **Max file size**: 
  - Free: 5MB
  - Pro: 50MB
  - Enterprise: 200MB

## 🏷️ Response Example

```json
{
  "success": true,
  "job_id": "job_65f3a2b1c4e5d",
  "status": "completed",
  "download_url": "https://pixzipai.io/download/abc123xyz",
  "original_size": 2458624,
  "compressed_size": 487265,
  "compression_ratio": 80.2,
  "processing_time": 1.24
}
```

## 💳 Rate Limits

| Plan | Requests/Hour | Max File Size | Concurrent Jobs |
|------|---------------|---------------|-----------------|
| Free | 60 | 5 MB | 1 |
| Pro | 600 | 50 MB | 10 |
| Enterprise | Custom | 200 MB | Unlimited |

## 🛠️ Error Handling

The API returns standard HTTP status codes:

- `200` - Success
- `201` - Job created
- `400` - Bad request
- `401` - Unauthorized
- `429` - Rate limit exceeded
- `500` - Server error

## 📦 Installation

### PHP
```bash
# No installation required, uses built-in cURL
php examples/php/basic-compression.php image.jpg
```

### Python
```bash
pip install requests
python examples/python/basic_compression.py image.jpg
```

### Node.js
```bash
npm install axios
node examples/nodejs/basic-compression.js image.jpg
```

## 🤝 Contributing

We welcome contributions! Please feel free to submit a Pull Request.

## 📄 License

MIT License - see [LICENSE](LICENSE) file

## 🆘 Support

- **Email**: support@pixzipai.io
- **Documentation**: https://pixzipai.io/help
- **API Status**: https://status.pixzipai.io

---

Made with ❤️ by the PixZipAI team
