# NPX Expo Commands Cheat Sheet

## Create Expo App
- **Install `create-expo-app` globally**:  
    ```bash
    npm install -g create-expo-app
    ```
> Once installed is not necessary to run above command again.

- **Create new project** 
```bash
npx create-expo-app --template
```
Then select the template option `Blank (TypeScript)`
And write your App name

## Development
- **Start the development server**:  
    ```bash
    npx expo start
    ```
- **Run on a specific platform**:  
    ```bash
    npx expo start --ios
    npx expo start --android
    npx expo start --web
    ```


## Debugging
- **Clear cache and start fresh**:  
    ```bash
    npx expo start -c
    ```

## Updates
- **Check for updates**:  
    ```bash
    npx expo upgrade
    ```

## Account Management
- **Login to Expo account**:  
    ```bash
    npx expo login
    ```
- **Logout from Expo account**:  
    ```bash
    npx expo logout
    ```

## Miscellaneous
- **Install Expo CLI locally (if needed)**:  
    ```bash
    npm install expo-cli
    ```
- **Check Expo CLI version**:  
    ```bash
    npx expo --version
    ```
