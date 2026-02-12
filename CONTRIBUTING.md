# Contributing to Bike API

Thank you for your interest in contributing to the Bike API project! We welcome developers from all skill levels to help improve this open-source bike database. This guide will help you understand how to contribute and how to integrate this data into your own projects.

---

## 📖 Table of Contents

1. [Code of Conduct](#code-of-conduct)
2. [Getting Started](#getting-started)
3. [How to Use This Repo in Your Project](#how-to-use-this-repo-in-your-project)
4. [How to Contribute](#how-to-contribute)
5. [Data Guidelines](#data-guidelines)
6. [Pull Request Process](#pull-request-process)
7. [Reporting Issues](#reporting-issues)
8. [Community](#community)

---

## 🤝 Code of Conduct

### Our Pledge

We are committed to providing a welcoming and inspiring community for all. Please be respectful and constructive in your interactions with other community members.

### Expected Behavior

- Use welcoming and inclusive language
- Be respectful of differing opinions and experiences
- Focus on what is best for the community
- Show empathy towards other community members
- Report inappropriate behavior to the maintainers

---

## 🚀 Getting Started

### Prerequisites

- Git installed on your machine
- Basic knowledge of JSON format
- A GitHub account
- A text editor (VS Code, Sublime Text, etc.)

### Setting Up Your Development Environment

1. **Fork the Repository**
   ```bash
   Click the "Fork" button on GitHub
   ```

2. **Clone Your Fork**
   ```bash
   git clone https://github.com/YOUR_USERNAME/bike-API.git
   cd bike-API
   ```

3. **Add Upstream Remote**
   ```bash
   git remote add upstream https://github.com/Kyl67899/bike-API.git
   ```

4. **Create a Feature Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

---

## 💻 How to Use This Repo in Your Project

### Option 1: Direct Data Import

Use the bike data directly in your JavaScript/Node.js project:

```javascript
// Import the bike data
import bikes from './path/to/data/bike.json';

// Use it in your application
bikes.forEach(bike => {
  console.log(`${bike.title} - $${bike.salePrice || bike.originalPrice}`);
});
```

### Option 2: As an API Server

Set up a local API server using JSON Server:

```bash
# Install json-server globally
npm install -g json-server

# Run the server
json-server --watch db.json

# Access the API
# GET http://localhost:3000/bikes
# GET http://localhost:3000/bikes?type=Mountain
# GET http://localhost:3000/bikes/1
```

### Option 3: NPM Package Integration

Install the repository as a dependency:

```json
{
  "dependencies": {
    "bike-api": "github:Kyl67899/bike-API"
  }
}
```

### Option 4: Fork & Customize

Fork this repository to create your own customized bike database:

1. Click "Fork" on the repository page
2. Make changes to fit your project needs
3. Deploy to your own server or use locally
4. Optionally, submit a pull request to contribute improvements back

### Option 5: Copy the Data Structure

Use this database schema as a template for your own bike API:

```json
[
  {
    "id": 1,
    "title": "Bike Name",
    "url": "https://image-url.com/bike.jpg",
    "details": "Description",
    "type": "Mountain",
    "originalPrice": 1000.00,
    "salePrice": 800.00,
    "rating": 4.5
  }
]
```

---

## 🔧 How to Contribute

### Types of Contributions We Accept

1. **New Bike Data** - Add authentic Trek bikes with accurate specifications
2. **Bug Fixes** - Fix errors in existing data
3. **Documentation** - Improve guides and examples
4. **Feature Requests** - Suggest improvements
5. **Performance Improvements** - Optimize data structure
6. **Integration Examples** - Add code examples for different frameworks

### Step-by-Step Contribution Guide

#### 1. Find an Issue or Create One

- Check [existing issues](https://github.com/Kyl67899/bike-API/issues)
- Comment on an issue to let others know you're working on it
- Or create a new issue describing your contribution

#### 2. Make Your Changes

**For Adding Bikes:**

```json
{
  "id": 89,
  "title": "Trek Bike Model Name",
  "url": "https://media.trekbikes.com/image/upload/...",
  "details": "Detailed description of bike features, frame material, components, etc.",
  "type": "Mountain|Road|Gravel|Hybrid|Kids|eBike",
  "originalPrice": 1299.99,
  "salePrice": 999.99,
  "rating": 4.5
}
```

**Files to Update:**
- `db.json` - Primary database
- `data/bike.json` - JavaScript export format

**Keep both files in sync!**

#### 3. Test Your Changes

Validate the JSON structure:

```bash
# Using Node.js
node -e "console.log(JSON.parse(require('fs').readFileSync('db.json', 'utf8')))"

# Ensure no syntax errors
npm test  # if available
```

#### 4. Commit Your Changes

```bash
# Stage your changes
git add db.json data/bike.json

# Commit with a clear message
git commit -m "Add 3 new Trek mountain bikes (IDs 89-91)"
```

**Commit Message Guidelines:**
- Be descriptive and specific
- Use present tense ("Add bikes" not "Added bikes")
- Reference any related issues: "Fix #123"
- Keep messages under 72 characters for the first line

Good examples:
- `Add Trek Slash 9.9 XT Gen 5 mountain bike`
- `Fix pricing for Domane ALR 5 #45`
- `Update bike ratings based on latest reviews`

#### 5. Push to Your Fork

```bash
git push origin feature/your-feature-name
```

#### 6. Create a Pull Request

1. Go to your fork on GitHub
2. Click "New Pull Request"
3. Select the original repository as the base
4. Fill out the PR template with:
   - **Title:** Clear description of changes
   - **Description:** Why this change? What bikes/data added?
   - **Related Issues:** Reference any issues
   - **Screenshots/Examples:** If applicable

---

## 📋 Data Guidelines

### Quality Standards

All contributed data MUST meet these requirements:

1. **Accuracy**
   - Information must come from official Trek Bike Store
   - Pricing should be current
   - Specifications must be correct

2. **Completeness**
   - All required fields must be filled
   - Descriptions should be detailed and informative
   - Images should be clear product photos

3. **Consistency**
   - Follow existing naming conventions
   - Use proper capitalization
   - Match the data structure exactly
   - Use consistent pricing format (2 decimal places)

4. **Uniqueness**
   - No duplicate bikes
   - Each bike should have a unique ID
   - Check existing data before adding

### Validation Checklist

Before submitting, verify:

- [ ] ID is unique and sequential
- [ ] Title is accurate and complete
- [ ] URL points to a valid image
- [ ] Details are descriptive (100+ characters recommended)
- [ ] Type is one of the allowed values
- [ ] originalPrice is a valid number
- [ ] salePrice is null or a valid number (must be less than originalPrice)
- [ ] rating is between 0-5 or null
- [ ] JSON syntax is valid
- [ ] Changes are in both db.json and data/bike.json
- [ ] No trailing commas
- [ ] No extra blank lines

---

## ✅ Pull Request Process

1. **Update Documentation** - Update README.md if needed
2. **Test Thoroughly** - Validate JSON and check for duplicates
3. **Self-Review** - Check your own code first
4. **Submit PR** - Fill out the PR template completely
5. **Respond to Feedback** - Be responsive to reviewer comments
6. **Keep Updated** - Rebase if main branch changes
7. **Merge** - Maintainers will merge when approved

### PR Template

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] New bike data
- [ ] Bug fix
- [ ] Documentation
- [ ] Other: ___

## Bikes Added/Modified
- ID: [bicycle title]

## How Has This Been Tested?
Describe the tests you ran and how to reproduce them.

## Checklist:
- [ ] My data follows the structure guidelines
- [ ] I have verified there are no duplicates
- [ ] I have updated both db.json and data/bike.json
- [ ] JSON syntax has been validated
- [ ] My changes generate no new warnings
```

---

## 🐛 Reporting Issues

### How to Report a Bug

1. **Check if issue exists** - Search existing issues first
2. **Provide details:**
   - What data has the problem?
   - What did you expect vs. what happened?
   - Steps to reproduce
   - Screenshots or examples

3. **Use the issue template:**

```markdown
## Description
Clear description of the issue

## Steps to Reproduce
1. ...
2. ...
3. ...

## Expected Behavior
What should happen

## Actual Behavior
What actually happens

## Data Affected
Bike ID(s) or bike title(s)

## Environment
- OS: [Windows/Mac/Linux]
- Browser/Editor: [if applicable]
```

---

## 🎯 Project Ideas

Want to contribute but not sure how? Here are some ideas:

1. **Add More Bikes** - Research and add new Trek models
2. **Create Integration Guides** - Write tutorials for React, Vue, Angular
3. **Build Tools** - Create scripts to validate or transform data
4. **Add Tests** - Write automated tests for data integrity
5. **Improve Documentation** - Add more examples and guides
6. **Create Filters** - Add filtering capabilities in examples
7. **Performance** - Optimize data structure for large datasets
8. **Translations** - Add multilingual support
9. **Mobile Examples** - Create React Native or Flutter examples
10. **Real-time API** - Deploy to Firebase, Vercel, or Heroku

---

## 🚀 Development Workflow Example

```bash
# 1. Fork and clone
git clone https://github.com/YOUR_USERNAME/bike-API.git
cd bike-API

# 2. Create a feature branch
git checkout -b feature/add-new-bikes

# 3. Edit files (add new bikes to db.json and data/bike.json)
# Use your preferred editor

# 4. Validate changes
node -e "console.log(JSON.parse(require('fs').readFileSync('db.json')))"

# 5. Commit and push
git add .
git commit -m "Add 5 new Trek endurance road bikes"
git push origin feature/add-new-bikes

# 6. Create Pull Request on GitHub
# Fill out the template and submit

# 7. Respond to reviews and make updates if needed
git add .
git commit -m "Address feedback: update bike descriptions"
git push origin feature/add-new-bikes
```

---

## 📚 Helpful Resources

- [GitHub: How to Fork a Repo](https://docs.github.com/en/get-started/quickstart/fork-a-repo)
- [GitHub: Creating a Pull Request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)
- [JSON Format Guide](https://www.json.org/)
- [Trek Official Website](https://www.trekbikes.com)
- [Markdown Guide](https://www.markdownguide.org/)

---

## 💡 Tips for Successful Contributions

1. **Start Small** - Begin with one or two bikes, not dozens
2. **Read First** - Understand the existing data structure
3. **Ask Questions** - Comment on issues or create discussions
4. **Be Patient** - Reviews may take time
5. **Learn & Grow** - Use this as an opportunity to learn
6. **Help Others** - Review other PRs when you can
7. **Stay Updated** - Keep your fork synced with main

---

## 🎓 Learning Resources

### If you're new to:

**Git & GitHub:**
- Git Tutorial: https://git-scm.com/book/en/v2
- GitHub Hello World: https://guides.github.com/activities/hello-world/

**JSON:**
- JSON Introduction: https://www.w3schools.com/js/js_json_intro.asp
- JSON Validator: https://jsonlint.com/

**Open Source:**
- Open Source Guide: https://opensource.guide/
- First Time Contributor: https://www.firsttimersonly.com/

---

## 👥 Community

- **Discussions** - Share ideas and ask questions
- **Issues** - Report bugs or request features
- **Pull Requests** - Contribute code and data
- **Twitter** - Follow updates @Kyl67899

---

## ✨ Recognition

Contributors will be recognized in:
- Pull Request comments
- Commit history
- Monthly contributor highlights

Thank you for making this project better! 🚴‍♂️

---

## 📞 Questions?

- Open an issue on GitHub
- Comment on related pull requests
- Check the main README.md for more info

**Happy contributing!** 🎉
