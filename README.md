name: Docker CI Pipeline



on:

&#x20; push:

&#x20;   branches:

&#x20;     - main



jobs:

&#x20; docker:

&#x20;   runs-on: ubuntu-latest



&#x20;   steps:

&#x20;   - name: Checkout Code

&#x20;     uses: actions/checkout@v4



&#x20;   - name: Setup Node.js

&#x20;     uses: actions/setup-node@v4

&#x20;     with:

&#x20;       node-version: '18'



&#x20;   - name: Install Dependencies

&#x20;     run: npm install



&#x20;   - name: Build Docker Image

&#x20;     run: docker build -t docker-pipeline .

