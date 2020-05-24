# my-first-docker-container
we build container that read one frame from video file on S3

install docker tutorial: https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04


# 1
cd my-first-docker-container

# 2
open the file Dockerfile and study the all lines

# 3
docker build -t my-first-docker-container .

# 4
run container and put the rasult on S3:

docker run \
    -e INPUT_VIDEO_FILE_URL='https://peleg-simple-site.s3-eu-west-1.amazonaws.com/video1.mp4' \
    -e POSITION_TIME_DURATION='00:08' \
    -e OUTPUT_THUMBS_FILE_NAME='testOnS3.png' \
    -e OUTPUT_S3_PATH='peleg-simple-site/folder' \
    -e AWS_REGION='eu-west-1' \
    -e AWS_ACCESS_KEY_ID='aaaaaaaaaaaaaaaaaaaaa' \
    -e AWS_SECRET_ACCESS_KEY='bbbbbbbbbbbbbbbbbbb/ccccccccccccccccccccccccccccccccaaa' \
    my-docker-ffmpeg-thumb

# 5
https://peleg-simple-site.s3-eu-west-1.amazonaws.com/folder/testOnS3.png
