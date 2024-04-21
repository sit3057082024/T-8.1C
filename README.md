# Teaching 305 708 TASK 8.1C Flask API

This Flask API leverages the GradientAI service with the Llama model to generate chat bot like responses

## Prerequisites

- Python 3.x installed on your system.

## Installation

1. Clone the repository.
2. Navigate to the directory.
3. Setup a virtual environment and install dependencies:

### MacOS and Linux

    ```bash
    python3 -m venv myenv
    source myenv/bin/activate
    pip install -r pip_install_commands.txt
    ```

### Windows

    ```bash
    python3 -m venv myenv
    myenv\Scripts\activate
    pip install -r pip_install_commands.txt
    ```

## Running the API

Execute the `main.py` script:

```bash
python main.py
```

The server will start on the default port 5000.

## API Endpoints

The API has two primary routes:

### Home Route: /

This route returns a welcome message and confirms that the API is operational.

Example Request:

```
curl http://localhost:5000/
```

Example Response:

```
Welcome to the Flask API!
```

### Get Quiz Route: /chat

This route accepts a POST request with a JSON payload containing the user's message and chat history. It processes the user's message and chat history to provide a response. The user must send a userMessage parameter as a string and a chatHistory parameter as a list of dictionaries with keys User and Llama.

Example Request:

```
POST: http://localhost:5000/chat
Data:
{
    "userMessage": "I do not have Pizza dough. Give instructions to make this pizza using bread",
    "chatHistory": [
        {
            "User": "Hello",
            "Llama": " Hello! Welcome to the chat! How can I assist you today? Is there something specific you would like to talk about or ask?"
        },
        {
            "User": "Give me instructtions to cook a pizza Give me instructtions to cook a pizza ",
            "Llama": " Great! I'd be happy to help you with that. Here are some basic instructions for cooking a pizza:\n\nIngredients:\n\n* Pizza dough (homemade or store-bought)\n* Pizza sauce\n* Mozzarella cheese (or your preferred cheese)\n* Toppings of your choice (e.g. pepperoni, mushrooms, onions, bell peppers, etc.)\n\nInstructions:\n\n1. Preheat your oven to 425-450°F (220-230°C).\n2. If using homemade dough, roll it out to your desired thickness and shape on a floured surface. If using store-bought dough, follow the package instructions for thawing and rising.\n3. Spread the pizza sauce over the dough, leaving a small border around the edges.\n4. Sprinkle the mozzarella cheese over the sauce, making sure to cover the entire surface.\n5. Add your desired toppings, making sure to leave enough space for the cheese to melt and the toppings to cook evenly.\n6. Bake the pizza in the preheated oven for 10-15 minutes, or until the crust is golden brown and the cheese is melted and bubbly.\n7. Remove the pizza from the oven and let it cool for a few minutes before slicing and serving.\n\nThat's it! Of course, you can always get creative with your toppings and add your own favorite ingredients to make the pizza your own. Enjoy!"
        }
    ]
}
```

Example Response:

```
{
    "message": " Great, no problem! You can definitely make a pizza using bread instead of dough. Here's how you can do it:\n\nIngredients:\n\n* Bread (any type will work, but a crusty bread like ciabatta or baguette works best)\n* Pizza sauce\n* Mozzarella cheese (or your preferred cheese)\n* Toppings of your choice (e.g. pepperoni, mushrooms, onions, bell peppers, etc.)\n\nInstructions:\n\n1. Preheat your oven to 425-450°F (220-230°C).\n2. Slice the bread into thin rounds, about 1/4 inch thick.\n3. Place the bread rounds on a baking sheet lined with parchment paper.\n4. Spread a layer of pizza sauce on each bread round, leaving a small border around the edges.\n5. Sprinkle mozzarella cheese over the sauce on each bread round.\n6. Add your desired toppings, making sure to leave enough space for the cheese to melt and the toppings to cook evenly.\n7. Bake the bread pizzas in the preheated oven for 10-15 minutes, or until the bread is crispy and the cheese is melted and bubbly.\n8. Remove the bread pizzas from the oven and let them cool for a few minutes before slicing and serving.\n\nThat's it! While the bread won't have the same texture as traditional pizza dough, it can still make for a delicious and easy pizza meal. Just be sure to use a bread that's sturdy enough to hold up to the toppings and the heat of the oven. Enjoy!"
}
```
