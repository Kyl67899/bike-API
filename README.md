# Bike API

A comprehensive, open-source bicycle database featuring real Trek bikes with detailed specifications, pricing, and product information. Perfect for developers building bike-related applications, e-commerce platforms, or cycling projects.

## 📌 Important Notice

**NOT SELLING BICYCLES** - This is a developer resource only. Data is based on official Trek bike specifications.

Follow my blog post on [dev.to](https://dev.to/kyl67899/bikeapi-1i7o) and [Hashnode.com](https://hashnode.com/@csdevfe) 

# Last updated:
May 23, 2026

---

## 🚀 Getting Started

### For Your Own Project

You can easily integrate this bike data into your project by:

1. **Forking the repository** and customizing the data
2. **Using the raw JSON data** directly in your application
3. **Contributing improvements** back to the project

### Quick Setup

```bash
# Clone the repository
git clone https://github.com/Kyl67899/bike-API.git
cd bike-API

# The data is available in two formats:
# - db.json (JSON database format)
# - data/bike.json (JavaScript export format)
```

---

## 📊 Data Structure

### Bike Object Schema

Each bike in the database contains:

```json
{
  "id": 1,
  "title": "Bike Model Name",
  "url": "https://image-url.com/bike-image.jpg",
  "details": "Detailed description of the bike specifications and features",
  "type": "Mountain|Road|Gravel|Hybrid|Kids|eBike",
  "originalPrice": 9999.99,
  "salePrice": 7999.99,
  "rating": 4.5
}
```

### Available Bike Types
- **Mountain** - Trail and XC bikes
- **Road** - Road racing and endurance bikes
- **Gravel** - Adventure and mixed-surface bikes
- **Hybrid** - Commuter and casual riding bikes
- **Kids** - Bicycles designed for children
- **eBike** - Electric-assisted bicycles

---

## 💻 Usage Examples

### JavaScript/Node.js

```javascript
import { bikes } from './data/bike.json';

// Get all bikes
console.log(bikes);

// Filter by type
const mountainBikes = bikes.filter(bike => bike.type === 'Mountain');

// Find a specific bike
const bike = bikes.find(bike => bike.id === 1);

// Get discounted bikes
const onSale = bikes.filter(bike => bike.salePrice !== null);
```

### Using with API Server (JSON Server)

If you have `json-server` installed:

```bash
npx json-server --watch db.json
```

Then access the API at `http://localhost:3000/bikes`

### React Example

```jsx
import { useState, useEffect } from 'react';
import bikes from './db.json';

function BikeList() {
  const [bikeList, setBikeList] = useState([]);

  useEffect(() => {
    setBikeList(bikes);
  }, []);

  return (
    <div>
      {bikeList.map(bike => (
        <div key={bike.id}>
          <h3>{bike.title}</h3>
          <p>{bike.details}</p>
          <span>${bike.salePrice || bike.originalPrice}</span>
        </div>
      ))}
    </div>
  );
}

export default BikeList;
```

---

## 📦 Data Files

- **`db.json`** - Complete bike database in JSON format (88 bikes)
- **`data/bike.json`** - JavaScript/ES6 export format
- **`bike.json`** - Raw bike data file

---

## 🔧 Customizing the Data

### Adding New Bikes

1. Open `db.json` or `data/bike.json`
2. Add a new bike object with the next available ID
3. Maintain the same structure and data types
4. Test your changes

### Example: Adding a New Bike

```json
{
  "id": 89,
  "title": "Your Bike Model",
  "url": "https://your-image-url.com",
  "details": "Bike description and specifications",
  "type": "Mountain",
  "originalPrice": 1299.99,
  "salePrice": 999.99,
  "rating": 4.5
}
```

---

## 🔗 API Resources

### Postman Collection

Test the API with our Postman collection:
[View on Postman](https://lunar-astronaut-205658.postman.co/workspace/My-Workspace~52dda099-49cc-4845-8494-bd6bad862ffc/api/f6c0087d-c003-44ae-819c-24b0a58bb3db/definition/e5e55f16-3340-4f04-af03-60f6751dc908/file/74b75aa9-73d9-413c-a6c9-daaeefca4b39)

---

## 📋 Current Dataset

- **Total Bikes:** 88
- **Categories:** Mountain, Road, Gravel, Hybrid, Kids, eBike
- **Latest Update:** February 2026
- **Data Source:** Official Trek Bike Store

---

## 🤝 Contributing

We welcome contributions! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/add-bikes`)
3. **Add or update bike data** in `db.json` and `data/bike.json`
4. **Commit your changes** (`git commit -m 'Add new Trek bikes'`)
5. **Push to the branch** (`git push origin feature/add-bikes`)
6. **Open a Pull Request**

### Contribution Guidelines

- Ensure all bike data comes from official sources (Trek Bike Store)
- Maintain consistent data structure and formatting
- Include accurate pricing and specifications
- Update both `db.json` and `data/bike.json` simultaneously
- Add meaningful commit messages

---

## 📄 License

This project is open source and available under the MIT License. See the LICENSE file for details.

---

## 🐛 Issues & Support

Found a bug or have a suggestion? Please [open an issue](https://github.com/Kyl67899/bike-API/issues) on GitHub.

---

## 👨‍💻 Author

**@Kyl67899**

---

## ✨ Recent Updates

- Added 18 new authentic Trek bike models (IDs 71-88)
- Enhanced documentation for developer integration
- Expanded bike categories to include Kids and expanded eBike selection
- Updated pricing and specifications from the official Trek store

---

**Happy coding! 🚴‍♂️**

Fork, custom code, and create. 

Join the [Discord](https://discord.gg/ZwQXnHWA) server.
