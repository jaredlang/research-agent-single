# The work is inspired by [JayZeeDesign researcher-gpt](https://github.com/JayZeeDesign/researcher-gpt)

* app.py is the original file
* app2.py is the file created by me based on langchain v0.2

## Key points

1. To test the FastAPI service
    * run uvicorn app2:api --reload
    * go to the swagger file under http://127.0.0.1/8000/docs
2. To run as streamlit webapp
    * uncomment the app function
    * run streamlit run app2.py
3. Import multiple versions of pydrantic
4. Use StructuredTool to create custom tools for agent
5. Create custom agent with custom tools and memory 
6. Use [Apify](https://apify.com) because
    * browserless costs too much
    * Apify actors are easier to integrate
    * But Apify webcrawler actor already summarizes the web content to some extent
7. To make it work on Windows 11, 
    * Set langsmith version to be 0.0.87 required by langchiain-core. 
    * Modify .venv\lib\site-packages\langchain_community\document_loaders\pebblo.py
    * Windows has no 'pwd' module. (Enjoy the open source)
    * Comment out 'import pwd' at line 5
    * Assign "unknown" to the document owner at line 264 
