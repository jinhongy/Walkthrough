
## Design for developers

Gemini Code Assist is a developer tool powered by Gemini. To ensure the best possible developer experience across their journey, we've supplemented the existing [Gemini design principles](https://carbon.googleplex.com/gem/pages/gemini-ux-principles/overview) with **developer-centric guidelines**. 


### Ensuring Coherency

To support developers working across diverse platforms, we separate product structure from its presentation. **Maintain a consistent information architecture and user flows** to ensure the experience is reliable and easy to learn. Simultaneously, **construct the UI using the native patterns** of the host OS to deliver a low-friction experience that feels like a natural part of the developer's environment.

Example

Unless dictated by platform, users should always be able to find the information they need in the same place across platforms. 



<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image1.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image1.png "image_tooltip")


Try this

Ensure consistent organization of information across all product touch points



<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image2.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image2.png "image_tooltip")


Don’t

Don't introduce unnecessary structural differences due to design preferences.



<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image3.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image3.png "image_tooltip")


Do

Prioritize familiar IDE interaction patterns developers already know.



<p id="gdcalert4" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image4.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert5">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image4.png "image_tooltip")


Don’t

Don't replace a standard component with a custom design without compelling reason.



<p id="gdcalert5" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image5.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert6">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image5.png "image_tooltip")


Don’t

Do not enforce consistency by forcing one platform's UI onto another.


### Maximizing Efficiency 

Designing for developers demands a **keyboard-first** experience. Developers operate primarily from the keyboard, by keeping developers on the keyboard, we not only preserve their focus and improve efficiency, but also enhance accessibility and streamline automation workflows.

Example

When Gemini offers code suggestions, immediately display visible keyboard shortcuts to accept, dismiss, or navigate them, encouraging quick adoption and seamless interaction.



<p id="gdcalert6" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image6.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert7">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image6.png "image_tooltip")


Do

Display keyboard shortcuts directly in menus and tooltips to encourage learning and adoption



<p id="gdcalert7" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image7.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert8">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image7.png "image_tooltip")


Don’t

Don’t force users to navigate deep menus for common actions.


### Building Trust

Developers trust systems they understand and can ultimately control. We build this by being **transparent about our system’s processes** and **ensuring the developer has the final control**. This empowers them to work with confidence, knowing they are always in command.

Example

Suggestions is presented as clear diff, giving the developer full control to accept, reject, or edit before committing.



<p id="gdcalert8" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image8.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert9">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image8.png "image_tooltip")


Do

Ensure developers can easily "undo" or "reject" any AI action.



<p id="gdcalert9" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image9.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert10">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image9.png "image_tooltip")


Don’t

Provide a black-box AI that gives suggestions without any explanation


## Gemini UX principles 

[Learn more ↗](https://carbon.googleplex.com/gem/pages/gemini-ux-principles/overview)


### Put the model first

Chatting with the model should be as easy as talking with a friend. Start with the model response, then use UI to enhance the conversation and help users take action on it.


### Make it simple

Thoughtfully leverage familiar patterns, invent only when necessary. Focus on the simplest solution to the core user problem, and avoid adding complexity.


### Get to value faster

Make sure the happy path is direct and unobstructed. Ruthlessly remove any friction that could get in the way of users’ end goal. 


### Be clear

Use clear, simple language everywhere. Disclaimers and terms should be easy to read and understand, building trust without being a burden.


### Sweat the details

Obsess about every detail, down to the word or pixel, considering solutions from multiple angles and relentlessly polishing until they shine.
