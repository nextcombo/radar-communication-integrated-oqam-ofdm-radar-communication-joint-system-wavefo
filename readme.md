# Radar Communication Integrated - OQAM-OFDM Radar-Communication Joint System Waveform Design [with MATLAB Code]

Keywords: Radar communication system, OQAM-OFDM based on Offset Quadrature Amplitude Modulation (OQAM), Information demodulation, Pulse compression, Signal-to-Noise Ratio (SNR), Cyclic algorithms and Alternate Direction Maximum Likelihood Algorithm (CA-ADMM).
1. In the past few decades, radar and communication have developed separately with different objectives. Radar is mainly used for detecting and tracking targets [1,2], while communication systems are primarily used for information transmission [3-7]. With the advancement of electronic technology, a device that utilizes both radar and communication has been developed for several applications, such as intelligent transportation systems [8] which need to perceive the environment and convey information. Therefore, the joint radar communication (RadCom) system can enjoy the advantages of reducing system weight, size, power consumption, etc., and has gained much interest in recent years [9].
Up to now, research on RadCom systems can be divided into two categories: non-simultaneous systems and simultaneous systems [10]. For non-simultaneous systems, radar and communication functions operate in different time slots [11]. Although it is easy to implement, there is a radar detection blind zone during the communication process, which also affects communication performance. On the contrary, simultaneous systems use shared signals, namely, RadCom signals, which can achieve both target detection and information transmission functions. Currently, there are three methods for designing RadCom signals. Firstly, radar and communication signals are independently generated and then superimposed [12,13]. Secondly, communication data is modulated on radar signals [14,15]. Thirdly, communication signals are designed as multi-carrier signals [16,17]. This method is considered the most promising one because it can provide high performance in both radar detection and information transmission.
Particularly, the orthogonal frequency division multiplexing (OFDM) waveform has been used by many studies as a RadCom signal [17-19]. In the literature [18], the author analyzed the feasibility of RadCom systems based on OFDM signals. The work in [19] achieved distance detection, synthetic aperture radar (SAR) imaging, and communication functions. Furthermore, in [17, 20-22], traditional OFDM schemes for RadCom systems based on cyclic prefix (CP) were proposed, which achieve good sidelobe performance and overcome multipath effects for radar detection. However, the presence of CP reduces spectral efficiency and consumes a significant amount of energy. Moreover, it is well known that OFDM signals may suffer from large sidelobes in the frequency domain, potentially leading to high inter-carrier interference (ICI) and out-of-band radiation [23, 24].
Recently, OFDM with OQAM (Offset Quadrature Amplitude Modulation) without CP has been studied as an alternative to OFDM [24-27]. Typically, a prototype filter with good frequency localization characteristics is applied to the OQAM-OFDM signal to present much lower sidelobes in the spectrum [26]. Based on this, the OQAM-OFDM waveform has been considered in multiple radar systems. The average speckle function of the OQAM-OFDM signal was derived in [29-31], and a perfect pin shape was presented in [32]. A M sequence-based OQAM-OFDM signal was proposed to improve signal correlation and radar range resolution.Furthermore, in [34], the use of an approximate range-interference (IRCI) free pulse compression method for low sidelobe OQAM-OFDM signals was examined. However, all the aforementioned studies applied only OQAM-OFDM signals to radar applications without considering communication functions.
In this paper, we propose a system that simultaneously performs radar and communication functions using OQAM-OFDM signals. The main contributions of this paper are summarized as follows:
1) We introduce an OQAM-OFDM RadCom signal based on traditional OQAM-OFDM signals which utilize the transmission sequence to carry information, leading to poor performance in RadCom systems. To improve performance, we introduce phase terms into the OQAM-OFDM signal to transmit information. Subsequently, the transmission sequences for each subcarrier can be designed to meet the requirements of radar and communication.
2) We propose a unified receiver signal model for the RadCom system. Recognizing each radar range cell as a communication path, the receiver signal model can be constructed as a convolution of the transmitted signal and channel response.
3) Different solutions are proposed for different targets of radar and communication, and their SNR performance is analyzed separately. Then, by designing the transmission sequence of the OQAM-OFDM signal, a method combining the cyclic algorithm and the alternating direction multiplier algorithm (CA-ADMM) is proposed to maximize the radar SNR and communication SNR.
Finally, numerical simulation results provide an evaluation of the effectiveness of the proposed plan. Simulation results show that our proposed CA-ADMM algorithm can improve the radar SNR and communication BER. Moreover, our proposed scheme provides superior performance over traditional methods.
For the remainder of this paper, we first derive the system model in Section 2. Then, in Section 3, we propose communication demodulation. In Section 4, we provide radar pulse compression. In Section 5, we design the joint RadCom OQAM-OFDM waveform. Numerical simulation results are provided in Section 6. Finally, in Section 7, we conclude this paper.
2. The system model shown in Figure 1 is the RadCom system, which supports radar and communication functions. By transmitting RadCom signals, we can detect targets by processing the echoes received by RadCom stations. Meanwhile, communication users receive RadCom signals and demodulate the transmitted information. In this paper, we introduce an OQAM-OFDM signal based on RadCom signals. Traditionally, in communication systems, each subcarrier of the OQAM-OFDM signal is used to carry information. In contrast, in our proposed RadCom system, we introduce a phase term into the OQAM-OFDM signal to carry information. Then, we can design the sequences on each subcarrier to optimize radar and communication performance, which will be discussed later.
Consider the OQAM-OFDM signal with K subcarriers, 2M OFDM symbols, and length Ls. The actual sequence transmitted on the kth subcarrier is represented as dk, which can be written as:
​  
Editor
​  
Editor
Figure 1 RadCom system schematic diagram
Among them, h(i) represents the symmetric real-valued prototype filter [28], and φk,m can be written as .
​  
Editor
Among them, θk,m ∈ (m ∈ = 0,1,...,M-1) are the information transmitted using phase shift keying (PSK) modulation. Therefore, even and odd symbols are respectively transmitted as the real and imaginary parts of ejθk,m. Consequently, we define the complex information to be transmitted as follows:
​  
Editor
For communication receivers, assuming the channel impulse response bcom r is known and of length Lcom v, the received signal v com i can be modeled as [33]
​  
Editor
Among them, Rcom is the length of bcom r, ωcom i represents additive white Gaussian noise with zero mean and variance σ2 com at the receiver. Similarly, for radar, given the transmitted signal si, the received signal vrad i at the RadCom station is represented as [34].
​  
Editor
Rrad represents the number of distance units, Bradr represents the response of scatterers within the rth distance unit, ωrad i is additive white Gaussian noise with zero mean and variance σ2 rad i at radar, Lrad v denotes the length of the received signal.
Note that for communication systems, the receiver demodulates signals in (4) to estimate ck,m. Meanwhile, for radar systems, to achieve target detection, pulse compression is necessary to enhance signal-to-noise ratio, which corresponds to detecting Brad r from the received signal in (5). For this reason, this paper conducts research on communication demodulation and radar pulse compression separately based on different targets of radar and communication systems.
3. Demodulation for communication systems in this section, we derive the method of obtaining the transmitted information from the received signal in (4). Firstly, we demodulate the received signal in (4)
​  
Editor
Assuming the length of the prototype filter Lh is much longer than the maximum delay spread Rcom, i.e., Lh > Rcom, the prototype filter function remains essentially unchanged within the delay spread [36].
Then, the ωk,m can be represented as demodulation noise, (6) which can be rewritten as [33,34]
​  
Editor
Among them, Bk corresponds to the frequency response of the channel.
​  
Editor
Ik, m.
​  
Editor
​  
Editor
​  
Editor
Here, Ik,m\zeta_{k,m}^{p,q}  are the imaginary values [34] of p,q ∈ Θp,q, thus Ik,m  is also imaginary.
Finally, we can get [35].
​  
Editor
Then, we can rebuild...
​  
Editor
From (12), we can demodulate the transmitted information. Additionally, to analyze the demodulation performance, we calculate the output SNR for each subcarrier as  .
​  
Editor
Among them, the noise variance of each subcarrier is noted. It is important to note that the communication output SNR of each subcarrier is related to the transmission sequence dk and the channel frequency response Bk. Therefore, we can design dk to improve SNRcom k, which will be discussed later.
4. Radar pulse compression In this section, we propose a simple and effective radar pulse compression method. According to (5), we rewrite the radar receiving signal in vector representation as follows:
​  
Editor
Among them, v = v0 v1 · · · vLrad ν −1 <$T ∈ CLrad ν  is the received signal vector, S ∈ CLrad ν ×Rrad  represents the transmitting signal matrix, which is given by:
​  
Editor
B = [b 0 b1 · · · bRrad−1]T ∈ CRrad indicates the vector corresponding to the distance unit, and w =<$ω0 ω1 · · · ωLrad ν −1 <$T ∈ CLrad ν represents the noise vector.
From equation (15), the columns of S are linearly independent. Therefore, SH\mathbf{S}^H\mathbf{S} is invertible.
Furthermore, in practical applications, the relationship Lrad ν > Rrad is evident. Subsequently, pulse compression can be easily achieved by estimating b, as shown in [37].
​  
Editor
Here, the noise covariance matrix becomes  .
Thus, the pulse compression is perfectly realized and there is no interference from other distance units for each distance unit estimation.
Similarly, we also derive the radar output SNR of the rth distance cell as follows:
​  
Editor
To achieve the maximum SNRrad r\mathrm{SNR}_{r}^{r\mathrm{ad}}, it can be proven that SHS should be diagonal [37]. However, typically, SHS can not be a diagonal matrix. Moreover, according to (15), it is evident that the diagonal elements of SHS are the same as those of SHS, where s = [s 0 s1 · · · sLs-1]T is the transmitted signal vector. Additionally, from (1), s can be represented as s = Φd, where Φ\mathbf{\Phi} is an Ls ×K matrix, with its (i, k)th element given as 
​
Edit
and d = [d 0 d1 · · · dK-1]T represents the OQAM-OFDM signal transmission sequence. Therefore, to maximize radar SNR, we can design d such that SHS satisfies the condition SHS <$2I. 
5.RadCom Joint Optimization Based on the derivation of RadCom signals in the previous section, we find that both radar SNR and communication SNR depend on d. In this section, we develop an optimization model to maximize radar SNR under the minimum communication SNR constraint, which can be written as 
​
Edit
​
​
Edit
where constraint (19 b) represents the energy constraint of the transmitted signal and SNRmin represents the acceptable output SNR for achieving a desired BER. Therefore, by solving problem (19), we not only maximize the radar SNR performance but also ensure the communication SNR performance. 
From (19), it is not easy to directly obtain the optimal solution for d. Therefore, we propose a CA-ADMM algorithm to solve problem (19). Please note that (19) aims to minimize the fourth power of S, which is difficult to handle. Thus, in [38, 39], similar methods are adopted, replacing (19)'s objective with 
​
Among them, Q is a semi-unitary matrix. Then, we can solve the problem (20) by using the CA algorithm [38].
Let us express
​  
Editor
As the singular value decomposition (SVD) of SH\mathbf{S}^H, where U ∈ CRrad×Rrad is an orthogonal matrix, V ∈ CRrad × Rrad is a diagonal matrix, and V ∈ CLrad v × Rrad is a semi-orthogonal matrix. Then, for given S, the solution to (20) can be given as:
​  
Editor
Therefore, based on (15), question (20) can be converted to  .
Among them, qr ∈ CLs×1 is a subvector of the rth column of <$Q$, with its position corresponding to the position of s in the rth column of S. Therefore, the final optimization model is used for optimizing
​  
Editor
Due to the non-convexity of constraints, Problem (24) is typically NP-hard [40, 41]. Therefore, we introduce the ADMM algorithm [42] to obtain the solution for Problem (24). Firstly, we develop the Augmented Lagrangian as follows.
​  
Editor
In which λ is a scalar vector of length Ls, αα represents the penalty factor. Then, the ADMM algorithm can be used to determine (s, d, λ) in an alternating manner to minimize L(s, d, λ) by considering the constraints in problem (24).
Let us represent s(t), d(t), λ(t), and q(t+1)r as the values of s, d, λ, and qr at the tth iteration. The value of q(t+1)r can be determined using equation (22) with s(t). Additionally, we can update s, d, and λ in the following manner:
​  
Editor
​  
Editor
​  
Editor
The detailed process for solving s(t+1) and d(t+1) is as follows:
5.1 Updating the state s with given d(t), λ(t), q(t+1)r
Ignore the constant term, the subproblem about s can be written as:
​  
Editor
Can be simplified to:
​  
Editor
Among them, x = λ(t) − αHΦd(t). Then, we can obtain a closed-form solution.
​  
Editor
5.2 Updating d given s(t+1), λ(t), q(t+1)
The subproblems containing dependent items on d are given by the following equation:
​  
Editor
So, the question in (31) can be represented as:
​  
Editor
Problem (32) can be solved by the coordinate descent (CD) algorithm [43, 44]. To update dk, we keep all other elements of d constant.
​  
Editor
Where a1, a2, and a3 are defined as a1 = [k]k, k,
​  
Editor
​  
Editor
​  
Editor
Therefore, we can obtain the solution for dk as follows:
​  
Editor
We continue the above process until all elements in d(t) are updated. Then, we finally obtain d(t+1).
The CA-ADMM algorithm for problem (19) is summarized in Algorithm 1, where the main computational complexity is related to the number of distance units Rrad and the iteration count. For each iteration, the main computational complexity corresponds to the SVD during the update of qr. Therefore, the proposed CA-ADMM algorithm requires O(F(Rrad)^3)O(F(R^{\mathrm{rad}})^3) computational complexity, where F represents the number of iterations.
6. Numerical Results
This section aims to evaluate the proposed RadCom design method based on CA-ADMM. We set the number of subcarriers as K = 128, the number of symbols as M = 4, the number of range units as Rrad = 64, and the channel length as Rcom = 6. The power distribution (in dB) is {-6.0, 0.0, -7.0, -22.0, -16.0, -20.0} and the corresponding delay distribution (in µs) is {-3, 0, 2, 4, 7, 11}. We use a binary phase shift keying (BPSK) modulation scheme. The raised cosine filter serves as the prototype filter for the OQAM-OFDM signal. d and λ are initialized randomly. All simulation results are obtained through Monte Carlo experiments with 100 trials.

Edited
Figure 2: Iteration residual κ with different α values
In Algorithm 1, the penalty factor α and the required minimum communication output SNRmin affect the performance of the proposed method. To verify this effect, Figure 2 shows the residual κ(t) = max s(t)−Φd(t), d(t)− d(t-1) with different α SNRmin = −30 dB, input SNR 0 dB). Here, for the CA-ADMM algorithm, the convergence threshold is set to 10^-4 [42, 45]. From Figure 2, it can be seen that when α is small, e.g., α = 10, 100, the proposed algorithm cannot guarantee convergence. If α is larger, then convergence can be ensured. Therefore, a larger α should be selected.In Figure 3, we present the variation of radar output SNR and Integrated Sidelobe Ratio (ISLR) with iteration number when the input SNR is 0 dB and SNRmin = −30 dB. It can be observed that the radar output SNR gradually increases with each iteration until it converges to SNRmax, which is the maximum achievable SNR. The SNRmax is calculated as the length of the transmitted signal. Additionally, as the number of iterations increases, ISLR decreases and rapidly converges. This algorithm achieves a gain of 4.35 dB compared to the uniterated case for output SNR and 3.73 dB for ISLR. Simultaneously, we can see that smaller values of α lead to rapid convergence.Additionally, under the conditions of an input SNR of 10 dB and SNRmin = −30 dB, the communication BER curve obtained through Monte Carlo experiments is shown in Figure 4. Similarly, we can observe that the BER performance improves with iteration. Therefore, it can be concluded that a suitable value for α must first be selected to ensure convergence, allowing the algorithm to converge as quickly as possible. We set α below 500 for simulation purposes. Moreover, from these curve graphs, we confirm that both radar and communication performance have been enhanced.
​  
Editor
Figure 4: Curve of communication error rate for different α values
Next, we analyze the impact of SNRmin. In Figure 5, residual κ with respect to iteration is depicted for different SNR min and input SNR of 0 dB. As expected, we can observe that the proposed algorithm converges gradually as iteration proceeds when SNRmin does not exceed the input SNR. For larger values of SNRmin, the time required for convergence is less, but when SNRmin is too large, the algorithm cannot converge. The reason for this is that larger SNRmin implies stronger communication constraints, leading to a reduction in the size of the feasible set.
​  
Editor
Figure 5: Residual κ under different SNRmin values
​  
Editor
Figure 6: Radar SNR relative to different SNRmin values in iterations
In Figures 6 and 7, radar and communication simulation results with different minimum signal-to-noise ratios (SNRmin) are presented. The radar's input SNR is 0 dB, while the communication's input SNR is 10 dB. As shown in Figure 6, the impact of SNRmin on radar performance is minimal, with all results converging quickly to SNRmax. In Figure 7, a larger SNRmin leads to better bit error rate (BER) performance. To this end, it is advisable to select the minimum SNR equal to the input SNR, which not only maximizes the radar output SNR but also significantly improves communication performance.
In Figures 8 and 9, we further analyze the radar and communication performance of different input SNRs when setting SNRmin as the input SNR. The results obtained with randomly generated d are used as a benchmark for comparison. In Figure 8, the proposed algorithm consistently achieves maximum SNR and outperforms traditional methods in both output SNR and ISLR performance. Compared to traditional schemes, the output signal-to-noise ratio gain of this algorithm is 4.43 dB, and the ISLR gain is 2.99 dB. Figure 9 presents the results of communication BER simulations. As the input signal-to-noise ratio increases, the proposed algorithm achieves significant performance gains compared to traditional methods. From the above simulation results, we verify the effectiveness of the proposed approach. Compared to traditional methods, this approach offers superior radar and communication performance.
​  
Editor
Figure 7: Communication Bit Error Rate for Different SNR Minimum Iterations
​  
Editor
Figure 8 Radar simulation results relative to the input SNR. (a) Output SNR (b) ISLR
​  
Editor
Figure 9: Communication BER results relative to input SNR
7. Conclusion This paper proposes a RadCom OQAM-OFDM joint system, which simultaneously achieves communication and radar pulse compression. A unified receiving signal model for radar and communication systems is established. To meet the needs of radar and communication, different methods are proposed to address this issue. The output signal-to-noise ratio (SNR) of the OQAM-OFDM signals is analyzed, revealing that the transmission sequence of the OQAM-OFDM signals is related to the radar SNR and communication SNR. By designing the transmission sequence, an optimization model is established to maximize the radar SNR while ensuring the minimum communication SNR. We employ the CA algorithm to transform the problem into a quadratic problem and then solve it under the framework of the ADMM algorithm. Finally, the effectiveness of this scheme is verified through numerical simulation results. Compared with traditional schemes, this method has superior radar SNR, sidelobe performance, and bit error rate performance.
​PartMATLABCodefunction [iterations, Zplot, SNRplot, SNRmaxplot, SNReqplot, ERRORplot, ERRORplot2, SS] = cyclic ()\n\n% Parameters\nK = 128;                        % # of subcarriers\nRcom = 6;                       % channel length\nRrad = 64;                      % # of range cells\nSNRin = 10;                     % input SNR = 10dB\nsigma = sqrt(1)/sqrt(K);        % std.\n\n% Communication Channel\nhdB = zeros(K, 1);\nhdB(1:Rcom, 1) = [-6.0 0.0 -7.0 -22.0 -16.0 -20.0];    % power profile\nh = zeros(K, 1);\nh(1:Rcom, 1) = 10.^(hdB(1:Rcom, 1)/10);\nH = fft(h);                                            % frequency response\n\n% Threshold\nSNRmin = 10.^(-20/10);                      % threshold SNR : -20dB per each subcarrier\nrho = sigma * sqrt(SNRmin) ./ abs(H);       % threshold power of each subcarrier rho = [rho(0) rho(1) ... rho(K-1)]\n\n% Initialization\nd = randn(K, 1) .* ((2 .* randi([0 1], K, 1) - 1) + 1i * (2 .* randi([0 1], K, 1) - 1));\nd = sqrt(SNRin) * d / norm(d);                % OFDM freq domain d = [d(0) d(1) ... d(K-1)]\n\ndd = zeros(K, 1);\nfor idx = 1 : K\n    dd(idx) = (2 .* randi([0 1], 1, 1) - 1) + 1i .* (2 .* randi([0 1], 1, 1) - 1);\n    dd(idx) = dd(idx) / norm(dd(idx));\nend\ndd = sqrt(SNRin) * dd / norm(dd);\n\nss = K * ifft(dd);\nS_S = zeros(K, Rrad);\nfor idx = 1 : Rrad\n    S_S(:,idx) = circshift(flipud(ss), K-Rrad+idx);\nend\n\nRand = orth(randn(K, K));\nQ = sqrt(K)* sqrt(SNRin) * Rand(:, 1:Rrad);            % semiunitary matrix\ns = K * ifft(d);                                       % OFDM time domain s = [s(0) s(1) ... s(K-1)]\nS = zeros(K, Rrad);\nfor idx = 1 : Rrad\n    S(:,idx) = circshift(flipud(s), K-Rrad+idx);\nend\n\n% Objective Function\ny = norm(S'*S - (Q'* Q), 'fro');\n\njdx = 0;\nz = y;\n\niterations = zeros(0, 0);\nZplot = zeros(0, 0);\nSNRplot = zeros(0, 0);\nSNRmaxplot = zeros(0, 0);\nSNReqplot = zeros(0, 0);\nERRORplot = zeros(0, 0);\nERRORplot2 = zeros(0, 0);\n\nwhile true\n    y = z;\n    % #1 : Obtain S given Q\n    S = alg1 (SNRin, K, Rrad, rho, Q, d);\n    \n    % #2 : Obtain Q given S\n    [U, ~, V] = svd(S');\n    Vtilde = V(:, 1:Rrad);\n    Q = sqrt(K) * sqrt(SNRin) * Vtilde * U';\n    \n    z = norm(S'*S - (Q'*Q), 'fro');\n    \n    SS = S' * S;\n    \n    SNRrad = sum(1 ./ diag(inv(S'*S))) / Rrad;\n    SNRraddB = 10 * log(SNRrad) / log(10);\n    \n    s = S(:,Rrad);\n    d = (1/K) * fft(flipud(s));\n    \n    SNRmax = 1 / norm(s).^(-2);\n    SNRmaxdB = 10 * log(SNRmax) / log(10);\n\n    SNReq = sum(1 ./ diag(inv(S_S' * S_S))) / Rrad;\n    SNReqdB = 10 * log(SNReq) / log(10);\n    \n    \n    SNRcom = abs(d).^2 .* abs(H).^2 / sigma^2;\n    ErrorP = sum(erfc(SNRcom ./ sqrt(2))) ./ K;\n    \n    SNRcom2 = abs(dd).^2 .* abs(H).^2 / sigma^2;\n    ErrorP2 = sum(erfc(SNRcom2 ./ sqrt(2))) ./ K;\n    \n    jdx = jdx + 1;\n    iterations = horzcat(iterations, jdx);\n    Zplot = horzcat(Zplot, z);\n    SNRplot = horzcat(SNRplot, SNRraddB);\n    SNRmaxplot = horzcat(SNRmaxplot, SNRmaxdB);\n    SNReqplot = horzcat(SNReqplot, SNReqdB);\n    ERRORplot = horzcat(ERRORplot, ErrorP);\n    ERRORplot2 = horzcat(ERRORplot2, ErrorP2);\n    \n    if abs(z-y) < 1e-5      % stopping criterion\n        break\n    end\n    \nend\n\nend\n  
​  

## Images

![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](01.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](02.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](03.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](04.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](05.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](06.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](07.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](08.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](09.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](10.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](11.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](12.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](13.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](14.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](15.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](16.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](17.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](18.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](19.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](20.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](21.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](22.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](23.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](24.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](25.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](26.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](27.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](28.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](29.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](30.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](31.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](32.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](33.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](34.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](35.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](36.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](37.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](38.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](39.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](40.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](41.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](42.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](43.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](44.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](45.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](46.png)
![(Radar Communication Integrated)OQAM-OFDM radar-communication joint system waveform design [with MATLAB code]](47.png)

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
