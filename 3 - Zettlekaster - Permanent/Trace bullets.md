Date: 2026-01-14
Tags: [[pragmatism]]

Connect the red dots as faster as possible
![[Pasted image 20260114091548.png]]

Given a project like Dropbox, instead of week by week build separately each box (frontend, backend, database...) with huge complex features, **start simple**, connect every dots first creating a backbone, then, full the with features.


Example:

Imagine you are building a system like Dropbox where users can upload files, the system scans them for viruses, and then stores them in the cloud.

#### ❌ The "Big Design" Approach (Risky)

1. **Week 1-2:** You design the perfect database schema for file metadata.
    
2. **Week 3-4:** You write the complex virus scanning algorithm.
    
3. **Week 5-6:** You build the frontend drag-and-drop interface.
    
4. **Week 7:** You try to connect them. _Disaster strikes: The frontend library you picked doesn't work with the backend API structure, and the virus scanner is too slow for real-time uploads._



#### ✅ The "Tracer Bullet" Approach

You decide to fire a tracer bullet first. Your goal is simply: **Can a user move 1 byte of data from the UI to the final storage?**

1. **Frontend:** You create a brutally ugly HTML page with one standard `<input type="file">` button.
    
2. **Backend:** You write a simple API endpoint that accepts the file.
    
3. **Logic:** You create a "dummy" virus scanner that just returns `true` (it doesn't scan anything yet, but the _interface_ is there).
    
4. **Database:** You save the file to a temporary folder on the server (not the complex cloud storage yet).
    

**The Result:** Even though it’s ugly and lacks features, you have proved that the **architecture works**. The UI can talk to the API, the API can talk to the Logic, and the Logic can write to the Storage.