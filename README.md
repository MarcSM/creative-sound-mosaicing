# Creative sound mosaicing with Freesound and Essentia

The idea of this concept is to basically download sound from Freesound, use Essentia to extract meaningful information from the input sound source and all the sounds retrieved from Freesound, and make a sound mosaic with the downloaded sounds tryng to reconstruct the original input sound.

## Project notes

### 1. Experiments carried out

Tons of tests were done with sounds of all kind, in fact the last recreation done (and the one that it is now by default on the jupyter notebook) uses query sounds such as “string”, “chicken”, “lion”. The ending result is pretty interesting and funny, in fact it can be used in a track, if you take this samples and process them a bit you can obtain very curious and decent results.

### 2. Collection of sources built

As it is mentioned, a lot of experiments were done with a lot of samples to see how diverse the ending result can be, whether the collection of sources is gone as it is overridden each time you query sounds to freesound, some of the results are still either in the “Output/Sounds” or the "mosaicing_examples" folders, so may be curious to check them out. The name of the generated files have a timestamp so you can run the algorithm as many times as you want without overriding and losing any result.

### 3. Target sounds

All the experimented target sounds are in the “Input” folder, notice that the sounds that are in the “Input/Sounds” folder are the ones that are actually retrived from freesound. It was also tried to not only use percussive stuff to see how the algorithm behaves but it gives best results with samples that has some kind of patterns and a lot of dynamics.

### 4. About the code

I’ve tried to do some kind of frequency content match with the help of the centroid function. As the centroid is a measure that indicates where the "center of mass" of the spectrum is, I thought it will be very convenient to use it to match source units with a similar frequency content.

I've also tried to make the reconstruction of the sound synchronous to the beat of the target signal by using the complex onsets methods from Essentia. I also had to add zero padding to the frames and control the frame length through the whole process, everything is properly documented within the code.

<a><img src="https://i.ibb.co/M7kHS65/Target-audio-file-Onsets.png" width="100%"></a>

## Setup and run

Please follow the instructions below to set up the required software in your computer and be able to run the notebooks.

### 1) Install Docker

It is recommended to read the documentation about [Docker](https://docs.docker.com/)
and [docker-compose](https://docs.docker.com/compose/).

#### Windows
https://docs.docker.com/docker-for-windows/install/

#### Mac
https://docs.docker.com/docker-for-mac/install/

#### Ubuntu
https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/#install-docker-ce

### 2) Install docker-compose

Follow [instructions](https://docs.docker.com/compose/install/).
Depending on your operartive system, this step won't be necessary because `docker-compose` will already have been installed in step 1).

### 3) Run the notebooks

Run the following command to startup the notebooks server:

    docker-compose up

Then access `http://localhost:8888` on your browser and when asked for a password use **mir**.