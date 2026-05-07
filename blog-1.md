🚀 How Pick and Omit Help Me Avoid Code Duplication in TypeScript
📖 Introduction
<p> While learning TypeScript, I realized that working with large interfaces often leads to repetition when I need slightly different versions of the same data. Writing separate interfaces again and again makes the code harder to maintain. </p> <p> To solve this problem, I started using TypeScript utility types like <strong>Pick</strong> and <strong>Omit</strong>. These utility types help me create smaller and reusable “slices” of a main interface without duplicating code. This also helps me follow the <strong>DRY (Don't Repeat Yourself)</strong> principle. </p>
❌ Problem I Faced Without Utility Types
<p> At first, I manually created multiple interfaces based on the same structure. </p>
interface User {
  id: number;
  name: string;
  email: string;
  password: string;
  createdAt: Date;
}
<p> Then I created another interface for public use: </p>
interface PublicUser {
  id: number;
  name: string;
  email: string;
}
<p> This caused several problems: </p> <ul> <li>🔁 I was repeating similar fields</li> <li>🛠️ If I changed <code>User</code>, I had to update multiple interfaces</li> <li>⚠️ It was easy to make mistakes or forget updates</li> </ul> <p> As a result, the code became harder to manage and maintain. </p>
✅ How <code>Pick</code> Helps Me
<p> <code>Pick</code> allows me to select only the properties I need from an existing interface. </p> <p> Instead of rewriting <code>PublicUser</code>, I can simply write: </p>
type PublicUser = Pick<User, "id" | "name" | "email">;
🧠 What I Learned
<ul> <li>♻️ I don’t need to rewrite fields again</li> <li>📦 I can reuse my original <code>User</code> interface</li> <li>🧹 My code becomes shorter and cleaner</li> </ul> <p> This is very useful when I only need a few properties from a large interface. </p>
✅ How <code>Omit</code> Helps Me
<p> <code>Omit</code> works in the opposite way. It removes specific properties from an interface. </p> <p> For example, if I do not want to expose the password field, I can write: </p>
type AdminUser = Omit<User, "password">;
🧠 What I Learned
<ul> <li>📌 I keep most of the original structure</li> <li>❌ I remove only the fields I don’t need</li> <li>🔒 It is safer for sensitive data like passwords</li> </ul>
🔥 How This Keeps My Code DRY
<p> By using <code>Pick</code> and <code>Omit</code>, I no longer duplicate interfaces. Instead, I create smaller versions from one main interface. </p> <p> This helps me: </p> <ul> <li>✅ Avoid repeating code</li> <li>✅ Make updates in one place only</li> <li>✅ Reduce errors and inconsistencies</li> <li>✅ Keep my project more organized</li> </ul> <p> This is a great example of following the <strong>DRY (Don't Repeat Yourself)</strong> principle in TypeScript. </p>
🏁 Conclusion
<p> Learning <code>Pick</code> and <code>Omit</code> made my TypeScript code cleaner and more professional. Instead of rewriting similar interfaces, I now create reusable types from a single source. </p> <p> These utility types help me reduce duplication, improve maintainability, and keep my code easier to understand. As I continue learning TypeScript, I find them very useful for writing scalable and organized applications. </p>