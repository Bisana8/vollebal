# vollebal
import requests

def get_number_of_volleyballs():
    url = 'https://volleyballstats.eu/api/volleyballs/europe'
    
    try:
        response = requests.get(url)
        data = response.json()
        number_of_volleyballs = data['volleyballs_count']
        return number_of_volleyballs
    except requests.exceptions.RequestException as e:
        print(f"Error fetching data: {e}")
        return None

# Example usage:
if __name__ == "__main__":
    number_of_volleyballs = get_number_of_volleyballs()
    if number_of_volleyballs is not None:
        print(f"Number of volleyballs in Europe: {number_of_volleyballs}")
    
 

