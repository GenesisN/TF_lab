# TF_lab
[2018-01-26 02:50:44 PM] *** disp("Hello World");
num1 = [2];
den1 = [1, 2];
G1 = tf(num1,den1);


num2= [-0.125, (-0.125*0.435)];
den2 = conv([1, 1.23], [1, 0.2265, 0.0169]);
G2 = tf(num2,den2);

new = series(G1,G2);

num3 = [-1];
den3 = [1];
G3 = tf(num3,den3);

feedbee1 = feedback(new,G3,-1);

num4 = [-1]; den4 = [1];
G4 = tf(num4,den4);

kG5 = series(feedbee1,G4);

finalfeedb = feedback(kG5,-1) 
