<h1>Passive Low Pass Filters</h1>

### [YouTube Demonstration In Work](INSERTLINK)

<h2>Description</h2>
A low-pass filter is an electronic circuit that allows signals with a frequency lower than a certain cutoff frequency to pass through while attenuating signals with higher frequencies. It's commonly used to remove high-frequency noise or to smooth out signals in applications such as audio processing, signal conditioning, and power supplies. These filters consist of passive components like resistors and capacitors and are essential in controlling the frequency response of electrical signals.
<br />

<h2>Environments Used</h2>
<b>- EasyEDA</b><br />
<b>- Excel</b><br />

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

<li><strong>Summary of Configurations</strong>
<ul>
  <li>RC Series Low-Pass Filter: Resistor in series, capacitor to ground.</li>
  <li>RC Parallel Low-Pass Filter: Resistor and capacitor in parallel, output across the capacitor.</li>
  <li>RL Series Low-Pass Filter: Inductor in series, resistor to ground.</li>
  <li>RL Parallel Low-Pass Filter: Inductor and resistor in parallel, output across the inductor.</li>
</ul>

<h2>Low-Pass Filter Analysis</h2>
