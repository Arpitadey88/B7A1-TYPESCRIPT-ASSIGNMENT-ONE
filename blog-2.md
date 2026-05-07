<h1>🚀 How Generics Help Me Build Reusable and Strictly Typed Code in TypeScript</h1>

<h2>📖 Introduction</h2>
<p>While learning TypeScript, I noticed that many functions and components repeat the same logic but work with different types of data. Writing separate functions for each type (like string, number, or object) makes the code repetitive and harder to maintain.</p>

<p>To solve this, I learned about <strong>Generics</strong>. Generics allow me to write reusable functions and components that still keep strict type safety, no matter what data type I pass in.</p>

<hr/>
<h2>❌ Problem Without Generics</h2>

<p>Before using Generics, I had to create separate functions for different data types, even when the logic was the same.</p>
<pre><code>function getString(value: string): string {  return value;}function getNumber(value: number): number {  return value;}</code></pre>

<p>This approach caused:</p>

<ul>  
    <li>🔁 Repeated code for similar logic</li>  
    <li>🧹 Poor code reusability</li>  
    <li>⚠️ More maintenance work when changes are needed</li>
</ul>

<p>Even though the logic was identical, I still had to write multiple functions.</p>

<hr/>

<h2>✅ How Generics Solve This Problem</h2>

<p>Generics allow me to create one reusable function that works with any data type while still keeping type safety.</p>

<pre><code>function getValue&lt;T&gt;(value: T): T {  return value;}</code></pre>

<p>Now I can use the same function for different types:</p>

<pre><code>getValue&lt;string&gt;("Hello");getValue&lt;number&gt;(100);getValue&lt;boolean&gt;(true);</code></pre>

<h3>🧠 What I learned:</h3>

<ul>  
    <li>🔄 <code>&lt;T&gt;</code> is a placeholder for a type</li> 
    <li>♻️ One function works for multiple data types</li> 
    <li>🔒 Type safety is still fully maintained</li>
</ul>

 <hr/>

 <h2>🔒 How Generics Stay Strictly Typed</h2>

 <p>Even though the function is flexible, TypeScript still knows the exact type being used.</p>

 <pre><code>const result = getValue&lt;string&gt;("TypeScript");</code></pre>

 <p>Here, TypeScript understands that <code>result</code> is a string. If I try to use it incorrectly (like applying number methods), TypeScript will show an error.</p>

 <p>This helps me catch mistakes early and write safer code.</p>

 <hr/>

 <h2>🔥 Benefits of Using Generics</h2>

 <ul>  
    <li>♻️ Reusable functions and components</li>  
    <li>🧹 Removes code duplication</li>  
    <li>🔒 Maintains strict type safety</li>  
    <li>⚡ Works with any data structure</li>  
    <li>📦 Useful in APIs, arrays, and reusable utilities</li>
 </ul>

 <hr/>

 <h2>🏁 Conclusion</h2>
 <p>Generics made my TypeScript code much more flexible and powerful. Instead of writing multiple versions of the same function, I can now write one reusable function that works with different data types while still keeping strict type checking.</p>
 <p>This helps me write cleaner, safer, and more scalable code, which is very important as my projects grow in size and complexity.</p>