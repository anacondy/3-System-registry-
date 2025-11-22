System Registry Protocol (SRP)Origin Project: Digital Denim OSCurrent Version: 1.0Protocol Trigger: C + O + 2 (Hold 2000ms)1. PurposeThe System Registry is a hidden, developer-focused metadata console. It serves as a persistent "signature" across all web and software projects. It allows the creator (and authorized users) to view the version history, build date, and installed feature set of any application without cluttering the main UI.2. The "CO2" Trigger MechanismThe feature is hidden by default (Dark Pattern).To activate:Press and hold the 'C' key.Press and hold the 'O' key.Press and hold the '2' key.Wait for 2 seconds while holding all three.Note: The specific key combination "CO2" is a mnemonic for "Code 2" or "Environmental/Live" mode, originating from the 'Digital Denim' environment logic.3. Aesthetic GuidelinesAny implementation of the System Registry must adhere to these styling rules to maintain continuity:Font: Monospace / Fixed-width (e.g., Courier New, Consolas, Roboto Mono).Background: Deep Black / Near Black (#0a0a0a or #000000).Borders: Subtle Industrial Grey (border-stone-700 or #444444).Primary Text: Dim Retro Grey (#d6d3d1).Accent Color: "Matrix" or "Terminal" Green (#10b981 or #34d399) used only for headers and active highlights.Vibe: "Read Only Memory", "Bios Screen", "Industrial Console".4. Data StructureThe Registry must verify and display the following object structure:{
  "version": 7,        // Natural Numbers Only (No decimals like 1.2)
  "date": "22 November 2025", 
  "protocol": "C+O+2 (Active)",
  "features": [
    "Feature Name A",
    "Feature Name B",
    "Feature Name C"
  ]
}
5. Integration GuideA. HTML / React ProjectsUse the SecretListener React hook (provided in system_registry.html). It utilizes the keydown and keyup event listeners to track a Set of pressed keys. A setTimeout triggers the modal state change.B. Python Projects (Desktop/GUI)If building with Tkinter, PyQt, or PyGame:Logic: You cannot easily track "holding for 2 seconds" natively in some simple scripts, so standard implementation often checks for the simultaneous press or a sequence.Library: Use the keyboard library for global hooks or specific event binding in your GUI framework.Python Mockup (Concept):import keyboard
import time

def on_activate():
    show_registry_window()

# Simple logic for detection
keys_pressed = set()

def check_keys():
    if {'c', 'o', '2'}.issubset(keys_pressed):
        time.sleep(2)
        if {'c', 'o', '2'}.issubset(keys_pressed):
            on_activate()
C. Python Projects (Web/Flask/Django)Since the frontend is HTML/JS, follow the HTML / React guide above and serve the JS listener file via your static folder.Saved to Memory: Yes.Status: Ready for Deployment.
