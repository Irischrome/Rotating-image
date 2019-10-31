# Rotating-image
MATLAB code for rotating an image without using imrotate

a. Algorithm for Image Rotation
	Read the original image. Let it be named as ‘img’
	Get the required angle of rotation in readians. We input it as ‘ang’
	Get the dimension of the image and classify it as ‘rowsi’ and ‘colsi.
	The final image dimensions can be found out by the formula
 	‘rowsf’ = (‘rowsi’ * abs(cos(ang)) + ‘cosli’*abs(sin(ang)))
	‘colsf’ = (‘rowsi’ * abs(sin(ang)) + ‘cosli’*abs(cos(ang)))
	Create an array C with dimensions rowsf and colsf and pad it with zeroes.
	Determine the mid-point coordinates (x0, y0) of the original image by multiplying it with half and similarly find out the mid-point coordinates (midx,midy) of final image by dividing the final image dimensions by 2.
	To rotate an image the transformation matrix id:
[■(cos⁡θ&sin⁡θ&0@sin⁡θ&-cos⁡θ&0@0&0&1)]

	since we want to map each coordinate in the final image with the corresponding coordinate in the original image, we will multiply the inverse of above matrix.
[■(cos⁡θ&-sin⁡θ&0@sin⁡θ&cos⁡θ&0@0&0&1)]
9. we also need to set the origin about the mid point of the final image, therefore we first shift the coordinates (i ,j ) of the final figure before multiplying with the inverse transformation matrix.
10. the resultant coordinates (x,y) which correspond to the original figure also needs to be shifted by the mid-point of the original figure.
11. the intensities of img(x,y) are then mapped to C(I,j).
