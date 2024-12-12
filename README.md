import requests

def get_mac_vendor(mac_address):
    url = f"https://api.macvendors.com/{mac_address}"
    response = requests.get(url)
    if response.status_code == 200:
        return response.text
    else:
        return "Manufacturer not found"

# Replace this with your router's BSSID (MAC address)
mac_address = "00:1a:2b:3c:4d:5e"
vendor = get_mac_vendor(mac_address)
print(f"Router Manufacturer: {vendor}")
