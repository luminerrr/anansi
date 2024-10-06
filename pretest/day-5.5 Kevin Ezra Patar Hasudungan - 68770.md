#### **Optional Questions:**

1. Which class is used to play audio files in Android?

   - a) `AudioPlayer`
   - b) `MediaRecorder`
   - c) `MediaPlayer`
   - d) `AudioRecorder`
   - e) `VideoView`
     Answer: C

2. What is the purpose of `VideoView` in Android?

   - a) To display and play audio files
   - b) To capture videos from the camera
   - c) To play video content
   - d) To stream live video
   - e) None of the above
     Answer: C

3. How do you capture images using the camera in Android?

   - a) Using `Intent.ACTION_IMAGE_CAPTURE`
   - b) Using `Intent.ACTION_VIDEO_CAPTURE`
   - c) Using `MediaRecorder`
   - d) Using `ImageView`
   - e) None of the above
     Answer: A

4. Which class is used for recording audio in Android?

   - a) `MediaPlayer`
   - b) `MediaRecorder`
   - c) `AudioRecorder`
   - d) `AudioCapture`
   - e) `SoundPlayer`
     Answer: B

5. What is the role of `setVideoURI()` in `VideoView`?
   - a) To start recording video
   - b) To set the path of the video to be played
   - c) To play audio content
   - d) To control audio playback
   - e) None of the above
     Answer: B

---

#### **True/False Questions:**

1. `MediaPlayer` is used for both playing and recording audio.
   Answer: False

2. The `VideoView` class requires a `MediaController` to play videos.
   Answer: False

3. You need runtime permissions to access the device's microphone or camera.
   Answer: True

4. The `MediaRecorder` class can be used to capture both audio and video.
   Answer: True

5. `ImageView` is used to capture images from the camera in Android.
   Answer: False

---

#### **Short Answer Questions:**

1. What is the purpose of `MediaPlayer` in Android?
   Answer: The `MediaPlayer` class is used to play audio and video files in Android. It provides methods to play, pause, stop, and seek to specific points in the media file.

2. How do you display and play a video in an Android app using `VideoView`?
   Answer: To display and play a video in an Android app using `VideoView`, you need to set the video URI using the `setVideoURI()` method and then call the `start()` method to begin playback.

3. Explain the process of capturing images using the camera in Android.
   Answer: To capture images using the camera in Android, you need to use the `Camera` class. First, you need to request runtime permissions to access the camera. Then, you can create a `Camera` object and use its methods to take a picture. Finally, you can save the captured image to a file.

4. What permissions are required to record audio in an Android app?
   Answer: To record audio in an Android app, you need to request the `RECORD_AUDIO` permission.

5. How can you play an audio file stored in the device’s raw resource directory?
   Answer: You can play an audio file stored in the device’s raw resource directory using the `MediaPlayer` class. First, you need to create a `MediaPlayer` object and then use its `set DataSource()` method to set the audio file as the data source. Finally, you can call the `prepare()` and `start()` methods to begin playback.

---

#### **Code Fix Questions:**

1. **Incorrect code:**

   ```kotlin
   val mediaPlayer = MediaPlayer()
   mediaPlayer.setAudioSource("audio.mp3")
   mediaPlayer.start()
   ```

   **Fix the code to correctly load and play an audio file using `MediaPlayer`.**

   **Correct code:**

   ```kotlin
   val mediaPlayer = MediaPlayer()
   mediaPlayer.apply {
      setDataSource(context, Uri.parse("audio.mp3"))
      prepare()
      start()
   }
   ```

2. **Incorrect code:**

   ```kotlin
   val videoView: VideoView = findViewById(R.id.videoView)
   videoView.setVideoPath("video.mp4")
   videoView.play()
   ```

   **Fix the code to correctly set and start video playback in a `VideoView`.**
   **Correct code:**

   ```kotlin
   val videoView: VideoView = findViewById(R.id.videoView)
   videoView.setVideoPath("android.resource://" + packageName + "/" + R.raw.video)
   videoView.start()
   ```

3. **Incorrect code:**
   ```kotlin
   val intent = Intent(MediaRecorder.ACTION_IMAGE_CAPTURE)
   startActivityForResult(intent, 1)
   ```
   **Fix the code to correctly capture an image using the camera intent.**
   **Correct code:**
   ```kotlin
   val intent = Intent(MediaStore.ACTION_IMAGE_CAPTURE)
   startActivityForResult(intent, 1)
   ```

---

### Project: Implementing Multimedia Features in an Android App

#### **Project Overview:**

Create an Android app that plays an audio file, displays a video, and allows the user to capture and display an image using the device’s camera.

---

#### **Task : Play Video using `VideoView`**

**Expectation:**

- Implement video playback using `VideoView`.
- Allow the user to load and play a video stored in the app’s resources.

**Step Details:**

1. Add a video file (e.g., `.mp4`) to the `res/raw` directory of your project.
2. In your activity, add a `VideoView` component to the layout.
3. Set the video source using `setVideoURI()` or `setVideoPath()`.
4. Add controls for the user to play and pause the video (using `MediaController` if necessary).
5. Ensure that the video starts and stops properly when the controls are used.

**Expected Outcome:**

- The user can play the video and control playback (play/pause) through the provided UI controls.

---
