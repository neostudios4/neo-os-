Please apply an absolute structural logic patch to the App Store and desktop shortcut components to add the updated Eaglercraft App configuration:

1. Target Path Realignment:
   - Configure the internal system shortcut and App Store downloader mapping for the 'Eaglercraft' app to point exactly to the specific PWA deployment client endpoint URL: "https://eaglercraft.com/play?source=pwa&version=26.2"

2. Isolation and Content Sandbox Containment:
   - When launching the application window, load the content inside a dedicated sandboxed iframe explicitly styled to lock mouse controls and prevent page navigation hooks from escaping into the user's real computer browser environment:
     <iframe src="https://eaglercraft.com/play?source=pwa&version=26.2" sandbox="allow-scripts allow-same-origin allow-pointer-lock" allow="fullscreen; autoplay; gamepad; pointer-lock" style="width:100%; height:100%; border:none;"></iframe>

3. Duplicate Shortcut Icon Prevention:
   - Within the installation loop script, ensure that if an application icon matching this specific ID is already present on the desktop canvas grid or taskbar state manager, the system immediately halts the appending layout cycle to stop redundant duplicates from spawning.
