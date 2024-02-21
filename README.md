# sandstorm
sandy video
git init
git add .
import cv2
import numpy as np

def generate_sandstorm(frame_size, duration, output_file):
    # Set the frame size and frames per second
    width, height = frame_size
    fps = 30

    # Create VideoWriter object
    fourcc = cv2.VideoWriter_fourcc(*'mp4v')  # You can change the codec as needed
    out = cv2.VideoWriter(output_file, fourcc, fps, (width, height))

    # Number of frames based on duration and fps
    num_frames = int(duration * fps)

    for frame_count in range(num_frames):
        # Generate a random sandstorm frame
        sandstorm_frame = generate_random_sandstorm_frame(frame_size)

        # Write the frame to the video file
        out.write(sandstorm_frame)

    # Release the VideoWriter object
    out.release()

def generate_random_sandstorm_frame(frame_size):
    # Create a black frame
    frame = np.zeros((frame_size[1], frame_size[0], 3), dtype=np.uint8)

    # Add random noise to simulate sand particles
    noise = np.random.randint(0, 255, frame_size, dtype=np.uint8)
    frame += noise

    # Optionally, you can apply other image processing techniques to enhance the sandstorm effect
    # For example, blurring or smoothing the image

    return frame

# Example usage:
frame_size = (1920, 1080)  # Set your desired frame size
duration = 10  # Set the duration of the sandstorm in seconds
output_file = 'sandstorm_green_screen.mp4'  # Set the output file name

generate_sandstorm(frame_size, duration, output_file)
git commit -m "Initial commit"
git push -u origin master
