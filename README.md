#DIGITAL IMAGE PROCESSING


## Periodic Noise Reduction 

## Fourier Tranformation & 2D Band-Reject & 2D Band-Pass Filters
## Also Low-Pass and High-Pass Filters are included

In this assignment we will try to reconstruct the image which have periodic noises on it. We
will use a special filters for reduction process but first we need to analyze the inputs. Input are
images as shown below.

As we see that, we have a challenge with three different type of periodic noises.

```
Vertical Periodic Noise
Horizontal Periodic Noise
Both Vertical and Horizontal Periodic Noise
```
We will be using Band-Reject (Notch) Filter to eliminate these noises. This filter rejects a chosen
frequencies from the frequency domain representation of the image.To perform this filter, we will
design an algorithm with following steps listed in below.

```
1)Apply Fourier Transform
2)Analyze the spectrum
3)Design the Band-Reject Filter
4)Apply the filter on the spectrum
5)Apply Inverse Fourier Transform to get clear output
```



```
We use the fft .fft2() and fft.ffshift() functions to apply Fourier Transformation. They came with numpy library.
```


We used the formula on the matrix of the first input’s spectrum. Firstly we took the spectrum of the
input. Then we copied the original spectrum and truncate coefficients and then we defined the
fraction of the coefficients in each directions.

After apply the filter, we took the inverse of the spectrum to get output.

For the last image (Both Vertical and Horizontal Noise), we use a little bit different version of the
filter which is used for the first and second input.

As we see in the spectrum, noises are different. We have to eliminate the frequencies most likely
responsible for noise (keep some low frequency components).(First Line)

We detect the sharp noise frequencies and reduce them.

Finally, we didn’t get perfect images but I think we cleaned the most of noises from the images and
at the end we have a more clear images then inputs.



