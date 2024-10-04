<h1>Passive Low Pass Filters</h1>

### [YouTube Demonstration](https://youtu.be/4LzXq5egAh8)

<h2>Description</h2>
<p>A low-pass filter is an electronic circuit that allows signals with a frequency lower than a certain cutoff frequency to pass through while attenuating signals with higher frequencies. It's commonly used to remove high-frequency noise or to smooth out signals in applications such as audio processing, signal conditioning, and power supplies. These filters consist of passive components like resistors and capacitors and are essential in controlling the frequency response of electrical signals.</p>

<h2>Environments Used</h2>
<ul>
  <li><b>EasyEDA</b></li>
  <li><b>Excel</b></li>
</ul>

<h2>Parts List</h2>
<ul>
  <li><strong>Capacitor (10uF)</strong>
    <ul>
      <li>Manufacturer: Nichicon</li>
      <li>Specifications: 10µF, 25V, Electrolytic</li>
      <li><a href="https://www.digikey.com/en/products/detail/nichicon/UCS2G100MPD1TD/3768673">Datasheet</a></li>
      <li>Supplier: Digikey</li>
    </ul>
  </li>
  <li><strong>Resistor (52Ω)</strong>
    <ul>
      <li>Manufacturer: BOJACK</li>
      <li>Specifications: 10kΩ, 1/4W, ±1%</li>
      <li><a href="https://www.amazon.com/BOJACK-Values-Resistor-Resistors-Assortment/dp/B08FD1XVL6/ref" target="_blank">Datasheet</a></li>
      <li>Supplier: Amazon</li>
    </ul>
  </li>
</ul>

<h2>Type of Low Pass Filters</h2>
<ul>
  <li><strong>RC Low-Pass Filter (Series)</strong>
    <ul>
      <li>Resistor in series, capacitor to ground:
        <ul>
          <li>The resistor is placed in series with the input signal.</li>
          <li>The capacitor is connected to ground.</li>
          <li>Behavior: At high frequencies, the capacitor's impedance decreases, shunting high-frequency signals to ground. Low-frequency signals pass through the resistor to the output.</li>
          <li>Application: Simple and common low-pass filter for attenuating high frequencies.</li>
        </ul>
      </li>
    </ul>
  </li>
  <li><strong>RC Low-Pass Filter (Parallel)</strong>
    <ul>
      <li>Resistor and capacitor in parallel:
        <ul>
          <li>The resistor and capacitor are both connected in parallel, with the input signal applied across them.</li>
          <li>The output is taken across the capacitor.</li>
          <li>Behavior: High-frequency signals are bypassed through the capacitor, while low frequencies remain across the capacitor (and across the resistor as well).</li>
          <li>Application: Less common than the series configuration but still behaves as a low-pass filter.</li>
        </ul>
      </li>
    </ul>
  </li>
  <li><strong>RL Low-Pass Filter (Series)</strong>
    <ul>
      <li>Inductor in series, resistor to ground:
        <ul>
          <li>The inductor is placed in series with the input signal.</li>
          <li>The resistor is connected to ground.</li>
          <li>Behavior: The inductor resists changes in current, allowing low frequencies to pass but impeding high-frequency signals. The resistor provides a path to ground for the high-frequency signals.</li>
          <li>Application: Commonly used in power applications or when high current handling is needed.</li>
        </ul>
      </li>
    </ul>
  </li>
  <li><strong>RL Low-Pass Filter (Parallel)</strong>
    <ul>
      <li>Inductor and resistor in parallel:
        <ul>
          <li>The inductor and resistor are connected in parallel, with the input applied across them.</li>
          <li>The output is taken across the inductor.</li>
          <li>Behavior: The inductor passes low frequencies and presents high impedance to high frequencies, allowing only low frequencies across it.</li>
          <li>Application: Like the parallel RC, this configuration is less common but still functions as a low-pass filter.</li>
        </ul>
      </li>
    </ul>
  </li>
</ul>

<h2>Summary of Configurations</h2>
<ul>
  <li>RC Series Low-Pass Filter: Resistor in series, capacitor to ground.</li>
  <li>RC Parallel Low-Pass Filter: Resistor and capacitor in parallel, output across the capacitor.</li>
  <li>RL Series Low-Pass Filter: Inductor in series, resistor to ground.</li>
  <li>RL Parallel Low-Pass Filter: Inductor and resistor in parallel, output across the inductor.</li>
</ul>

<h2>Background</h2>
<p>For my low-pass filter, I used a configuration of a resistor and a capacitor in series with one another, with the resistor coming before the capacitor, and the output voltage being measured across the capacitor. The behavior of RC components in relation to signal frequencies helps explain why this functions as a low-pass filter.</p>
<ul>
  <li>Resistors' impedance remains constant regardless of the signal frequency.</li>
  <li>Capacitors, however, block high-frequency signals because their impedance decreases at higher frequencies. At low frequencies, the capacitor has a higher impedance, so it allows more of the low-frequency signal to appear across it.</li>
</ul>
<p>In this scenario, the filter works as a low-pass filter because, at high frequencies, the capacitor's impedance is low, allowing the high-frequency signal to bypass the output. Meanwhile, at low frequencies, the capacitor’s impedance is high, so most of the signal voltage is dropped across the capacitor, resulting in the low-frequency signal being passed to the output.</p>

<h2>Motivation</h2>
<p>However, you may ask, at what point does the filter decide what is a low-frequency signal and what is a high-frequency signal? That is defined by the cutoff frequency. The cutoff frequency is determined based on the value of the resistor and capacitor that you chose and is calculated using the below formula:</p>
<img src="https://github.com/user-attachments/assets/51e86869-7400-42ba-883b-bc56991d7783"/>

<h2>Experiment</h2>
<h3>Setup</h3>
<p>For my low-pass filter, I used a 51-ohm resistor and a 10uF capacitor, meaning that my expected cutoff frequency in a perfect world would be roughly 312 Hz.</p>
<img src="https://github.com/user-attachments/assets/28ad9e8b-e691-403b-8c73-03647f9d3ce6"/>
<p>To test this, I made my own low-pass filter (which can be seen in the simple schematic above) and then connected the input voltage to a wave generator and the output voltage to an oscilloscope. I also connected the input voltage straight from the wave generator to the oscilloscope so I could see both waves side by side. I took readings of the amplitude of the output voltage (peak to peak) and the phase shift (more on why later) at various frequencies. Once I gathered the amplitude readings (along with the phase shift readings), I derived the gain from them. My results are pictured below along with corresponding graphs.</p>

<h2>Results</h2>
<img src="https://github.com/user-attachments/assets/b65ac26e-7c32-4c78-ac12-d8d41ba54d85"/>

<h2>Gain Analysis</h2>
<p>As you can see from the Gain vs. Frequency graph, there appears to be a drop-off between 400 and 1000 Hz. Signals with a frequency greater than 1000 Hz appear to be significantly attenuated, while signals with an amplitude less than 400 Hz have only minor attenuation. In other words, only signals less than 400 Hz (around the cutoff frequency) pass through relatively unattenuated.</p>
<ul>
  <li><strong>Low Frequencies (100 Hz - 400 Hz):</strong>
    <ul>
      <li>The gain values at these lower frequencies are between -9.12 dB and -12.40 dB, which means that the filter is allowing these lower frequencies to pass with only mild attenuation. A high-pass filter would typically attenuate lower frequencies more aggressively, rather than allowing them to pass with relatively modest losses.</li>
    </ul>
  </li>
  <li><strong>Higher Frequencies (1000 Hz and above):</strong>
    <ul>
      <li>From 1000 Hz onward, the gain sharply decreases to -28.87 dB and eventually stabilizes around -30.17 dB. This significant attenuation of higher frequencies is the key indicator of a low-pass filter, as it demonstrates that the filter is strongly reducing the amplitude of signals in the higher frequency range.</li>
    </ul>
  </li>
</ul>

<h2>Phase Shift Analysis</h2>
<p>As you can see from the Phase Shift vs. Frequency graph, there appears to be a steady decline in the amount the output voltage lags the input voltage until about 1000 Hz, where the trend levels out.</p>
<ul>
  <li><strong>Low Frequencies (100 Hz - 400 Hz):</strong>
    <ul>
      <li>The phase shift in this range is relatively small, hovering between -10 and -20 degrees. This small lag suggests that the filter is passing the input signal relatively faithfully at lower frequencies, with only minor phase distortion.</li>
    </ul>
  </li>
  <li><strong>Higher Frequencies (1000 Hz and above):</strong>
    <ul>
      <li>Above 1000 Hz, the phase shift sharply increases, indicating a growing lag of around -70 degrees at 2000 Hz. This greater lag is a sign of the filter’s increasing difficulty in tracking the input signal, resulting in greater phase distortion for higher frequency components.</li>
    </ul>
  </li>
</ul>

<h2>Conclusion</h2>
<p>In conclusion, the low-pass filter constructed using a 51-ohm resistor and a 10uF capacitor successfully attenuates high-frequency signals while allowing lower frequency signals to pass relatively unattenuated. The cutoff frequency calculated aligns with the observed results, demonstrating the practical effectiveness of passive RC low-pass filters in signal processing applications.</p>

<h2>Future Work</h2>
<p>Future improvements could include experimenting with different resistor and capacitor values to modify the cutoff frequency further, utilizing more complex filter designs to achieve sharper roll-offs, or integrating operational amplifiers to create active low-pass filters with improved performance.</p>
