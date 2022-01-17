# Eye Blink Detection Framework

Implements a blink detection tracking framework based on facial landmarks

- Uses dlib (2d detection in Grey Color Space) with the shape_predictor_68_face_landmarks model. [1,4]

- Uses mediapipe for debug face mesh output overlay (can be disabled for performance sensitive deployments) [3]


## Logic

- If eyes closed is detected for NOTIFICATION_SECONDS (e.g. 4), a telegram alert is dispatched
- After alert has been dispatched, notifications are blockedun less the user unblocks the system by closing eyes again for NOTIFICATION_SECONDS


## Issues

- Glasses can interfere with detection
- Racial features / skin tones may affect performances.

## Future Improvements


- switch from dlib to mediapipe [2] for detection (works in 3d space, doesn't need beefy model download). 
  - This should provide superior performance, especially for low contrast situations

## Requirements

```
python 3 + pip
python-dotenv
opencv-python (cv2)
mediapipe
dlib
```

## Installation

1. Create a .env file with 

```
BOT_TOKEN=Your telegram bot token
CHAT_ID=Your telegram chat recipient
```
2. Run the notebook

3. Profit

## References

[1] https://medium.com/algoasylum/blink-detection-using-python-737a88893825
[2] https://towardsdatascience.com/face-landmark-detection-using-python-1964cb620837
[3] https://www.analyticsvidhya.com/blog/2021/07/facial-landmark-detection-simplified-with-opencv/
[4] https://www.pyimagesearch.com/2017/04/24/eye-blink-detection-opencv-python-dlib/
