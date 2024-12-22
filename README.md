# AnyDietAI
This is a project for the Neural Networks discipline designed to suggest healthier meals to users, primarily in Portuguese. The application leverages the <a href="https://www.kaggle.com/datasets/shrutisaxena/food-nutrition-dataset">Food Nutrition Dataset</a> to tailor meal suggestions based on user descriptions, dietary preferences, and any food restrictions related to conditions like diabetes, hypertension, or celiac disease. Each food nutrient (carbohydrate, protein, fat, vitamins, etc.) is scored on a scale from -1 (completely avoid) to 1 (strongly recommended), ensuring the recommendations align with the user's health needs.

Foods in the dataset are ranked based on their nutritional profiles and organized using a Kohonen map (SOM). When the user specifies what they'd like to eat, the system uses embeddings to identify the closest matching foods in the dataset. It then suggests healthier alternatives by selecting foods near the user's choice on the SOM projection, ensuring they are nutritionally similar but better aligned with the user's health goals. Finally, an LLM generates a meal plan incorporating these healthier options.

To run the project, first install the dependencies:

```pip install -r requirements.txt```

Then, execute the file with the home page:

```streamlit run login.py```

You will need two tokens: one from <a href="https://huggingface.co/">HuggingFace</a> to use the all-MiniLM-L6-v2 embeddings model, and another from <a href="https://console.groq.com/keys">Groq Cloud</a> to make requests to Llama-3-8b.

If you don't want to run it locally, it's also available on <a href="https://anydietai.streamlit.app/">Streamlit Cloud</a>
