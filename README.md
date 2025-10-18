import requests
import json

def get_weather(city):
    api_key = "YOUR_API_KEY"
    base_url = f"http://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}&units=metric"
    response = requests.get(base_url)
    data = response.json()
    return data

def display_weather(data):
    print(f"City: {data['name']}")
    print(f"Temperature: {data['main']['temp']}°C")
    print(f"Humidity: {data['main']['humidity']}%")
    print(f"Weather: {data['weather'][0]['description']}")

city = input("Enter an Indian city name: ")
data = get_weather(city)
display_weather(data)
