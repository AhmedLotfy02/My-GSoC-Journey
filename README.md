<h1 align="center">
    <br>
    <a href="https://ibb.co/QbHsHBH">
        <img src="https://i.ibb.co/6nt6tht/Screenshot-from-2024-08-22-21-41-13.png" alt="Screenshot" border="0">
    </a>
    <br>
</h1>

<h1 align="center">
    <a href="https://ibb.co/6P5smr9">
        <img src="https://i.ibb.co/0M3Jcm4/image-6.jpg" alt="image-6" width="800" border="0">
    </a>
</h1>

<h4>السلام عليكم</h4>
<h4>احسب ان هذه الفرصة هي خير و نعمة من الله فالحمدلله الذي رزقني هذا فما توفيقي الا به و ما توكلي الا عليه </h4>

<h1>Welcome to My GSoC Journey with Keploy 🐰!</h1>

<h1 align="center">
    <a href="https://ibb.co/HFSFT7Y">
        <img src="https://i.ibb.co/j6N6khG/image-7.jpg" alt="image-7" border="0">
    </a>
</h1>

<p>👋 Hello and welcome to my project for <strong>Google Summer of Code (GSoC)</strong>! I'm excited to share with you the journey of building contract testing capabilities for <strong>Keploy</strong>, a powerful open-source tool designed for automated end-to-end test generation, mocking, and test management.</p>

<p>Through this project, I worked on enhancing Keploy by implementing <strong>contract testing</strong> features that automate the validation of interactions between different services. This ensures seamless communication through APIs, reducing the risk of integration errors and service downtimes.</p>

<p>In the sections below, I will walk you through the features of the project, how the schema matching and scoring systems work, and the value this project adds to the software development process. I'm also excited to share how this experience has helped me grow technically and professionally during GSoC.</p>

<h2>📑 Table of Contents</h2>
<ul>
    <li><a href="#proposal">My Proposal</a></li>
    <li><a href="#key-features">Key Features</a></li>
    <ul>
        <li><a href="#generate-contracts">Generate Contracts</a></li>
        <li><a href="#download-contracts">Download Contracts</a></li>
        <li><a href="#validate-contracts">Validate Contracts</a></li>
        <li><a href="#support-http-methods">Support for Multiple HTTP Methods</a></li>
        <li><a href="#openapi-integration">OpenAPI Integration</a></li>
        <li><a href="#mock-generation">Mock Generation for Testing</a></li>
    </ul>
    <li><a href="#matching-and-scoring">Matching and Scoring</a></li>
    <li><a href="#sample">Sample</a></li>
    <li><a href="#code">Code</a></li>
    <li><a href="#value-added">Value Added</a></li>
</ul>

<h2 id="proposal">My Proposal</h2>
<p>You can find my proposal in this repo or ask me if you have any questions.</p>

<h2 id="key-features">Key Features 🚀</h2>

<h3 id="generate-contracts">1. Generate Contracts</h3>
<p>The <code>generate</code> command allows users to create contracts for specified services. It auto-generates contracts based on the HTTP methods (like <code>GET</code>, <code>POST</code>, etc.), request body, response status, and body. This checks if the services behave according to expectations in terms of their input/output interactions.</p>

<p><strong>Command Example:</strong></p>
<pre><code>keploy contract generate</code></pre>

<p>When executed, this command will:</p>
<ul>
    <li>Capture HTTP requests and responses</li>
    <li>Generate contracts in OpenAPI formats</li>
    <li>Save these contracts for future use (validation, mocking, etc.)</li>
</ul>

<h1 align="center">
    <a href="https://ibb.co/sP7pyn4">
        <img src="https://i.ibb.co/mBpr6kK/Screenshot-from-2024-08-22-22-51-14.png" alt="Screenshot" border="0">
    </a>
</h1>

<h3 id="download-contracts">2. Download Contracts</h3>
<p>The <code>download</code> command fetches contracts for specific services from either remote repositories or local configurations. This helps maintain consistency across different environments (development, testing, production).</p>

<p><strong>Command Example:</strong></p>
<pre><code>keploy contract download --driven "consumer" --path /local/path</code></pre>

<p>When executed, this command will:</p>
<ul>
    <li>Download contracts from the specified path or repository</li>
    <li>Ensure consistent versioning across testing and production environments</li>
    <li>Make these contracts available for validation or mock generation</li>
</ul>

<h3 id="validate-contracts">3. Validate Contracts</h3>
<p>The <code>validate</code> command checks whether the service's behavior matches the generated contract. It ensures no unexpected changes occur in the service's communication patterns, reducing API-breaking changes.</p>

<p><strong>Command Example:</strong></p>
<pre><code>keploy contract validate --driven "consumer" --path /local/path</code></pre>

<p>When executed, this command will:</p>
<ul>
    <li>Compare the current service behavior against the contract</li>
    <li>Log and report any discrepancies</li>
    <li>Help identify if any API-breaking changes have occurred</li>
</ul>

<h1 align="center">
    <a href="https://ibb.co/1s0nTYg">
        <img src="https://i.ibb.co/jV85D9N/Screenshot-from-2024-08-22-23-16-20.png" alt="Screenshot" border="0">
    </a>
</h1>

<h3 id="support-http-methods">4. Support for Multiple HTTP Methods</h3>
<p>This project supports multiple HTTP methods, including <code>GET</code>, <code>POST</code>, <code>PUT</code>, <code>DELETE</code>, and <code>PATCH</code>. It automatically maps request parameters such as headers, query parameters, and path variables, validating the structure of the response.</p>

<h3 id="openapi-integration">5. OpenAPI Integration</h3>
<p>The system integrates with OpenAPI for contract generation and validation. HTTP requests and responses are converted into OpenAPI documentation, ensuring standardized contract storage and validation in OpenAPI format.</p>

<h3 id="mock-generation">6. Mock Generation for Testing</h3>
<p>The <code>mock</code> feature generates mock data based on service contracts. This allows testing services in isolation without needing real service dependencies, improving the testing process.</p>

<h2 id="matching-and-scoring">Matching and Scoring 🎯</h2>

<h3>Matching Overview</h3>
<p>The matching process compares mock and test services' request and response bodies, headers, parameters, and status codes. The goal is to ensure that both mock and test operations behave similarly, adhering to the expected contract.</p>

<p>The matching is carried out by:</p>
<ul>
    <li>Comparing the operation types (GET, POST, etc.) to ensure they match</li>
    <li>Comparing the request bodies and validating JSON structures using schema comparison tools</li>
    <li>Comparing parameters such as headers, query parameters, and path variables to ensure they align</li>
    <li>Comparing response bodies, status codes, and content</li>
    <li>Handling discrepancies using diff tools to highlight differences in the request/response payloads</li>
</ul>

<h3>Scoring System</h3>
<p>The scoring system evaluates how closely the test service adheres to the contract. It assigns a score based on the similarity of the expected and actual outputs. Here's how the scoring is calculated:</p>

<ul>
    <li><strong>Operation Matching:</strong> If the mock and test operations (GET, POST, etc.) match, a higher score is assigned.</li>
    <li><strong>Request Body Matching:</strong> The system compares the JSON structures of the request body. If the structures are identical, a higher score is given. The system uses JSON diff tools to calculate the differences between the expected and actual JSON.</li>
    <li><strong>Response Body Matching:</strong> The similarity between the response bodies (in terms of status code, body content, and headers) also impacts the score. A close match will result in a higher score, while differences will reduce the score.</li>
    <li><strong>Parameter Matching:</strong> Parameters such as headers, query parameters, and path variables are compared. Matching parameters contribute to a higher score.</li>
</ul>

<h3>Score Calculation</h3>
<p>The score is normalized and expressed as a percentage. A score close to 100% indicates that the test service adheres closely to the contract, while lower scores indicate discrepancies.</p>

<p>For instance:</p>
<ul>
    <li>A match in operation types contributes a fixed percentage (e.g., 30%).</li>
    <li>A match in request body structure adds another percentage (e.g., 40%).</li>
    <li>A match in response body structure adds the remaining percentage (e.g., 30%).</li>
</ul>

<h3>Error Handling</h3>
<p>In case of mismatches or errors during comparison, the system logs detailed reports and differences between the expected and actual values. This helps developers understand where the mismatches occurred and take appropriate action.</p>

<h2 id="sample">🎯 Sample</h2>
<h4>You can run a sample from this <a href="https://github.com/AhmedLotfy02/Consumer-Driven-Contract-Testing-Sample">repo</a></h4>

<h2 id="code">Code 💻</h2>
<h4>You can take a look <a href="https://github.com/keploy/keploy/pull/2010">here</a></h4>

<h2 id="value-added">💡 Value Added</h2>

<h3>1. Automated Contract Verification</h3>
<p>This project automates contract validation, reducing the manual effort required in integration testing. It automatically checks service compatibility against existing contracts.</p>

<h3>2. Improved Service Integration</h3>
<p>By ensuring services do not break integration points, contract testing reduces integration issues in microservice architectures.</p>

<h3>3. Prevents Breaking Changes</h3>
<p>The project highlights and prevents changes that violate the service contract, ensuring API stability and backward compatibility.</p>

<h3>4. Faster Development Cycles</h3>
<p>By validating contracts early, teams can resolve integration issues before they reach production, leading to faster and more reliable development cycles.</p>

<h3>5. Mocking for Independent Testing</h3>
<p>Mock data generation allows developers to simulate service interactions, enabling isolated testing without dependencies on real services.</p>

<h3>6. OpenAPI Compliance</h3>
<p>By using OpenAPI standards, this system ensures interoperability with various tools and services, automating the generation of OpenAPI documentation from service behaviors.</p>

<h3>7. Cross-Environment Consistency</h3>
<p>The system ensures that contract testing can be consistently applied across different environments (development, testing, production).</p>

<h3>8. Clear Reporting</h3>
<p>Detailed reports are generated during validation, highlighting passed, failed, and missed test cases for easy debugging and triaging.</p>
