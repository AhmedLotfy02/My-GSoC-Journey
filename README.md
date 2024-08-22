<h1 align="center">
    <br>
    <a href="https://ibb.co/QbHsHBH"><img src="https://i.ibb.co/6nt6tht/Screenshot-from-2024-08-22-21-41-13.png" alt="Screenshot-from-2024-08-22-21-41-13" border="0"></a>
    <br>
</h1>

<h1 align="center">

<a href="https://ibb.co/6P5smr9"><img src="https://i.ibb.co/0M3Jcm4/image-6.jpg" alt="image-6" width="800" border="0"></a>
</h1>

<h1>Welcome to My GSoC Journey with Keploy 🐰!</h1>
<p>
Hello and welcome to my project for <strong>Google Summer of Code (GSoC)</strong>! I'm excited to share with you the journey of building contract testing capabilities for <strong>Keploy</strong>, a powerful open-source tool designed for automated end-to-end test generation, mocking, and test management.
</p>
<p>
Through this project, I worked on enhancing Keploy by implementing <strong>contract testing</strong> features that automate the validation of interactions between different services. This ensures seamless communication through APIs, reducing the risk of integration errors and service downtimes.
</p>
<p>
In the sections below, I will walk you through the features of the project, how the schema matching and scoring systems work, and the value this project adds to the software development process. I'm also excited to share how this experience has helped me grow technically and professionally during GSoC.
</p>

<h2>Table of Contents</h2>
<ul>
<li><a href="#overview">Overview</a></li>
<li><a href="#key-features">Key Features</a></li>
<ul>
<li><a href="#generate-contracts">Generate Contracts</a></li>
<li><a href="#schema-matching">Schema Matching</a></li>
<li><a href="#scoring-system">Scoring System</a></li>
</ul>
<li><a href="#installation">Installation and Setup</a></li>
<li><a href="#usage">Usage</a></li>
<ul>
<li><a href="#contract-generation">Contract Generation</a></li>
<li><a href="#schema-validation">Schema Validation</a></li>
</ul>
<li><a href="#conclusion">Conclusion</a></li>
</ul>

<h2 id="overview">Overview</h2>
<p>
<strong>Contract Testing</strong> ensures that different services can interact seamlessly by verifying that APIs adhere to specified contracts. This type of testing minimizes integration errors that can occur when services are updated independently, potentially breaking the established communication paths between them.
</p>

<h2 id="key-features">Key Features</h2>

<h3 id="generate-contracts">1. Generate Contracts</h3>
<p>
The <code>generate</code> command allows users to create contracts for specified services. Contracts are auto-generated based on HTTP request and response behaviors, such as HTTP methods (GET, POST, etc.), request body, response status, and body. This process validates whether the services behave as expected in terms of their input/output interactions.
</p>
<pre>
<code>
Example Command:
$ keploy generate -s <service-name>
</code>
</pre>

<h3 id="schema-matching">2. Schema Matching</h3>
<p>
Schema matching compares the contract of the mock service against the actual service using various criteria like request bodies, parameters, and response bodies. This process ensures that both services are aligned, reducing the risk of breaking changes.
</p>
<p>In schema matching, the following aspects are compared:</p>
<ul>
<li>Request bodies (marshaled and validated)</li>
<li>Response bodies (by status code)</li>
<li>Parameters (like headers and query params)</li>
</ul>

<h3 id="scoring-system">3. Scoring System</h3>
<p>
The scoring system evaluates the similarity between mock responses and actual responses. It calculates the percentage match based on key-value pairs of the schema. A higher score means better contract alignment between services.
</p>
<p>Key factors that affect the score:</p>
<ul>
<li>Exact matches for schema elements</li>
<li>Ordering of JSON fields (if required)</li>
<li>Handling noisy fields (ignored during comparison)</li>
</ul>

<h2 id="installation">Installation and Setup</h2>
<p>
Follow the steps below to install and set up Keploy for contract testing.
</p>
<ol>
<li>Clone the repository from GitHub.</li>
<li>Install the required dependencies using <code>go get</code>.</li>
<li>Build the project using <code>go build</code>.</li>
</ol>

<h2 id="usage">Usage</h2>

<h3 id="contract-generation">1. Contract Generation</h3>
<p>
Generate contracts for your service using the following command:
</p>
<pre>
<code>
$ keploy generate -s <service-name>
</code>
</pre>

<h3 id="schema-validation">2. Schema Validation</h3>
<p>
Validate the schema between your mock and actual service by comparing the generated contracts:
</p>
<pre>
<code>
$ keploy validate -c <contract-file> -s <service-name>
</code>
</pre>

<h2 id="conclusion">Conclusion</h2>
<p>
Thank you for following along with my GSoC journey! I hope you found the contract testing features helpful for ensuring smooth integration between services in your projects. Feel free to explore the repository, try out the commands, and reach out with any questions or feedback.
</p>

