# Expo AsyncStorage Silent Failure on Missing Key

This repository demonstrates a common, yet subtle, bug in Expo's AsyncStorage: the silent failure when attempting to retrieve a non-existent key.  The issue lies in the lack of explicit error handling for this specific scenario.  The provided code showcases the problem and its solution.

## Problem

When using AsyncStorage.getItem to retrieve a value associated with a key that doesn't exist, AsyncStorage doesn't throw an error.  Instead, it simply returns null, making it hard to identify and handle this situation within the application flow.

## Solution

The solution involves explicitly checking for null after retrieving the value from AsyncStorage and handling the case where the key is not found. This allows for graceful handling of missing keys, preventing unexpected behavior.