Download link : https://programming.engineering/product/com-sgn-110-exercise-8/

COM-SGN.110-EXERCISE 8
The tasks should be completed and presented to TA during the lab session. Do not forget to upload your solutions to Moodle! Questions about exercises should be addressed to the TA personally, through Moodle messages or via email, which can be found on the Moodle page of the course.

1. Image Blurring

(Hint: If division by values close to zero causes problems, add a small constant value to the denominator.)

a. Implement a motion blurring filter as follows:

            	

            T

            H (u , v ) =
            	

            (ua + vb) sin (ua + vb ) exp( − j (ua + vb)),

where T is the exposure time of the camera and a and b are the total distances covered by the motion of the imaged objects relative to the camera, in time T, in the x and y directions respectively. We will blur the image in the 135º direction (considering the unit circle) by using T=1 and the total distances covered by the motion set to 0.1.

(Hint: Use meshgrid to obtain the 2D grid coordinates as follows:

[u, v] = meshgrid(-row/2:row/2-1, -col/2:col/2-1);)

    Apply H(u,v) to the image DIP.jpg to generate a motion blurred image. (Note: filtering in DFT domain, Ex6_DFT.pdf is attached for reference)

    Apply inverse filtering to restore the image.

    Display the original image, motion blurred image (1b) and the restored image (1c) in a row subplot. Also calculate and display the Mean Squared Error values of the motion blurred and the restored image with respect to the original. (help immse)

2. Image Restoration via Wiener Filtering

    Add noise to the blurred image (1b) with zero mean and a variance of 50. (help randn)

    Apply simple inverse filtering to the degraded image (2a).

    Apply the Wiener filter:

                														

                ˆ
                	

                1
                				

                H (u , v)
                		

                2
                			
                		
                							

                F (u , v ) =
                													

                G (u , v)
                											

                H (u , v)
                			

                H (u , v)
                		

                2
                	

                +
                	

                S n
                	

                (u , v)
                		
                											
                								
                									

                S f
                	

                (u , v)
                							

    Display the degraded image (2a), result of inverse filtering(2b) and the result of Wiener filtering (2c) in a row sub-plot.

    Explain why simple inverse filtering generally cannot recover problems such as in Task 2a.

    What would the restoration using the Wiener Filter look like if, as in most cases, you do not know Sn and Sf. Show results using three different values of k (= Sn/Sf). Compare to 2c.

