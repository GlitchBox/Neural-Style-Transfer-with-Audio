# Neural-Style-Transfer-with-Audio
I attempted to apply Neural Style Transfer for audio clips. This would follow the same priniciples as style transferring with images. The system would take a content audio clip and a style audio clip. The resultant audio would contain the same contents (e.g. the same words spoken) as the content audio but follow the style (e.g. the pitch, timbre etc). 

For example, let's say the content audio contains me saying 1 to 10. The style audio contains the voice of Batman. The result should be someone saying 1 to 10 in Batman's voice. I have attempted to achieve this two ways. 

## First attempt
First I split the audio clips to segments of 0.5 seconds. Then each segment was transformed from Time domain to frequency domain (MelSpectogram). The transformed segments then would be fed to the encoder-decoder network. The decoder should return our desired audio clip. However, I have used LSTM layers in both the encoder and the decoder network. I later realized that LSTM layers had no bearing on this encoding-decoding process. None of the spoken words didn't depend on what was said before, nor it did have any influence on what came after. The network was simply supposed to reconstruct each segment with style applied. Anyway, this way didn't work out. Gibberish was produced with high pitched noices at particular times in the audio. These spikes occurred around times when words were said in the real audio. I will replace the LSTM layers with FC layers, get larger dataset and try again.

## Second attempt
I replaced the LSTM layers with FC layers. I have yet to build a decoder. This is a work in progress and I will keep updating.
