# Design for developers

Gemini Code Assist is a developer tool powered by Gemini. To ensure the best possible developer experience across their journey, we've supplemented the existing Gemini design principles with **developer-centric guidelines**. 

|Put the model first | Make it simple | Get to value faster | Be clear |  Sweat the details |
| :--- | :--- | :--- | :--- | :---|
| Chatting with the model should be as easy as talking with a friend. Start with the model response, then use UI to enhance the conversation and help users take action on it.  | Thoughtfully leverage familiar patterns, invent only when necessary. Focus on the simplest solution to the core user problem, and avoid adding complexity. | Make sure the happy path is direct and unobstructed. Ruthlessly remove any friction that could get in the way of users’ end goal. | Use clear, simple language everywhere. Disclaimers and terms should be easy to read and understand, building trust without being a burden. | Obsess about every detail, down to the word or pixel, considering solutions from multiple angles and relentlessly polishing until they shine. |


## Principle 1: Ensuring Coherency

To support developers working across diverse platforms, we separate product structure from its presentation. **Maintain a consistent information architecture and user flows** to ensure the experience is reliable and easy to learn. 

Simultaneously, **construct the UI using the native patterns** of the host OS to deliver a low-friction experience that feels like a natural part of the developer's environment. For example, unless dictated by platform, users should always be able to find the information they need in the same place across platforms. 

<br>

|<img src="https://drive.google.com/file/d/1ecrUC7-lAlqkNWrJY6W8iKAqLXswV72n/view?usp=drive_link&resourcekey=0-Kt8hBAc_G1SH6p2JCM-Z-g" alt="Consistent UI example" width="250"> |<img src="path/to/your_consistent_image.png" alt="Consistent UI example" width="250"> |<img src="path/to/your_consistent_image.png" alt="Consistent UI example" width="250"> |
| :--- | :--- | :--- |
| ✅ Prioritize familiar IDE interaction patterns developers already know. | ❌   Don't replace a standard component with a custom design without compelling reason. | ❌  Do not enforce consistency by forcing one platform's UI onto another. |


## Principle 2: Maximizing Efficiency 

Designing for developers demands a **keyboard-first** experience. Developers operate primarily from the keyboard, by keeping developers on the keyboard, we not only preserve their focus and improve efficiency, but also enhance accessibility and streamline automation workflows. For example, when Gemini offers code suggestions, immediately display visible keyboard shortcuts to accept, dismiss, or navigate them, encouraging quick adoption and seamless interaction.

|<img src="path/to/your_consistent_image.png" alt="Consistent UI example" width="250"> |<img src="path/to/your_consistent_image.png" alt="Consistent UI example" width="250"> |
| :--- | :--- | 
| ✅ Display keyboard shortcuts directly in menus and tooltips to encourage learning and adoption  | ❌  Don’t force users to navigate deep menus for common actions. | 


## Principle 3:Building Trust

Developers trust systems they understand and can ultimately control. We build this by being **transparent about our system’s processes** and **ensuring the developer has the final control**. This empowers them to work with confidence, knowing they are always in command. For example, suggestions is presented as clear diff, giving the developer full control to accept, reject, or edit before committing.

<br>

|<img src="path/to/your_consistent_image.png" alt="Consistent UI example" width="250"> |<img src="path/to/your_consistent_image.png" alt="Consistent UI example" width="250"> |
| :--- | :--- |
| ✅  Ensure developers can easily "undo" or "reject" any AI action. | ❌   Provide a black-box AI that gives suggestions without any explanation | 
