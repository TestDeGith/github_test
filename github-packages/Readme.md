export GH_USERNAME='herpriz2'
export GH_TOKEN='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'
GH_IMAGE_NAME='hello-world'
export GH_VER='1.0.0'
export TAG_NAME="ghcr.io/$GH_USERNAME/GH_IMAGE_NAME:$GH_VER"

echo $GH_TOKEN | docker login ghcr.io -u $GH_USERNAME --password-stdin

docker tag hello-world:latest $TAG_NAME

docker push $TAG_NAME

LABEL org.opencontainers.image.source https://github.com/OWNER/REPO