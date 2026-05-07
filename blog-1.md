<h1>🚀 How <code>Pick</code> and <code>Omit</code> Help Me Avoid Code Duplication in TypeScript</h1>

<h2>📖 Introduction</h2>
<p>
While learning TypeScript, I realized that working with large interfaces often leads to repetition when I need slightly different versions of the same data. Writing separate interfaces again and again makes the code harder to maintain.
</p>

<p>
To solve this problem, I started using TypeScript utility types like <strong>Pick</strong> and <strong>Omit</strong>. These help me create smaller, reusable “slices” of a main interface without duplicating code. This also helps me follow the <strong>DRY (Don't Repeat Yourself)</strong> principle.
</p>

---

<h2>❌ Problem I Faced Without Utility Types</h2>
<p>
At first, I manually created multiple interfaces based on the same structure.
</p>

<pre><code>
interface User {
  id: number;
  name: string;
  email: string;
  password: string;
  createdAt: Date;
}
</code></pre>

<p>
Then I created another interface for public use:
</p>

<pre><code>
interface PublicUser {
  id: number;
  name: string;
  email: string;
}
</code></pre>

<h3>⚠️ Problems I faced:</h3>
<ul>
  <li>🔁 Repetition of similar fields</li>
  <li>🛠️ If I changed <code>User</code>, I had to update multiple interfaces</li>
  <li>❌ Easy to forget updates or make mistakes</li>
</ul>

<p>
This made my code less efficient and harder to maintain.
</p>

---

<h2>✅ How <code>Pick</code> Helps Me</h2>
<p>
<code>Pick</code> allows me to select only the properties I need from an existing interface.
</p>

<p>
Instead of rewriting, I can do this:
</p>

<pre><code>
type PublicUser = Pick&lt;User, "id" | "name" | "email"&gt;;
</code></pre>

<h3>🧠 What I learned:</h3>
<ul>
  <li>♻️ I don’t need to rewrite fields again</li>
  <li>📦 I reuse my original <code>User</code> interface</li>
  <li>🧹 My code becomes shorter and cleaner</li>
</ul>

<p>
This is very useful when I only need a few fields from a large object.
</p>

---

<h2>🔒 How <code>Omit</code> Helps Me</h2>
<p>
<code>Omit</code> works in the opposite way. It removes specific fields from an interface.
</p>

<p>
For example:
</p>

<pre><code>
type AdminUser = Omit&lt;User, "password"&gt;;
</code></pre>

<h3>🧠 What I learned:</h3>
<ul>
  <li>📌 I keep most of the original structure</li>
  <li>❌ I remove only what I don’t need</li>
  <li>🔐 It is safer for sensitive data like passwords</li>
</ul>

---

<h2>🔥 How This Keeps My Code DRY</h2>
<p>
By using <code>Pick</code> and <code>Omit</code>, I no longer duplicate interfaces. Instead, I depend on one main <code>User</code> interface and derive smaller versions from it.
</p>

<h3>✔️ This helps me:</h3>
<ul>
  <li>Avoid repeating code</li>
  <li>Make updates in one place only</li>
  <li>Reduce errors and inconsistencies</li>
  <li>Keep my project more organized</li>
</ul>

<p>
This is a practical example of following the <strong>DRY (Don't Repeat Yourself)</strong> principle in TypeScript.
</p>

---

<h2>🏁 Conclusion</h2>
<p>
Learning <code>Pick</code> and <code>Omit</code> made my TypeScript code cleaner and more professional. Instead of rewriting similar interfaces, I now create reusable types from a single source.
</p>

<p>
This approach saves time, reduces duplication, and makes my code easier to maintain as my projects grow.
</p>