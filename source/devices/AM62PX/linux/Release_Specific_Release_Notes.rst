.. _Release-note-label:

#############
Release Notes
#############

Overview
========

The **Processor Software Development Kit (Processor SDK)** is a unified software platform for TI embedded processors
providing easy setup and fast out-of-the-box access to benchmarks and demos.  All releases of Processor SDK are
consistent across TI’s broad portfolio, allowing developers to seamlessly reuse and develop software across devices.
Developing a scalable platform solutions has never been easier than with the Processor SDK and TI’s embedded processor
solutions.

To simplify the end user experience, Processor SDK Linux AM62Px installer provides everything needed as discussed below
to create the embedded system from “scratch” :

-  Platform/board-support software and configuration files for Linux
-  U-Boot and Kernel sources and configuration files
-  An ARM cross-compiling toolchain as well as other host binaries and components
-  A Yocto/OE compliant filesystem and sources for example applications
-  A variety of scripts and Makefiles to automate certain tasks
-  Other components needed to build an embedded system that don’t fit neatly into one of the above buckets
-  Reference Examples, benchmarks

This release supports High Security - Field Securable (HS-FS) devices.

Licensing
=========

Please refer to the software manifests, which outlines the licensing
status for all packages included in this release. The manifest can be
found on the SDK download page or in the installed directory as indicated below.

-  Linux Manifest:  :file:`<PSDK_PATH>/docs/software_manifest.html`


Release 10.00.07.04
===================

Released on August 2024

What's new
----------

**Processor SDK Linux AM62Px Release has following new features:**

  - LTS Refresh with Stable Kernel update to 6.6.32
  - Important Bug Fixes on top of Processor SDK 09.02.01.10 Release
  - `CC33XX M.2 Module <https://www.ti.com/tool/M2-CC3351>`__ Wi-Fi support on `SK-AM62P-LP <https://www.ti.com/tool/SK-AM62P-LP>`__ - :ref:`How to Enable M.2-CC33x1 in Linux <enable_m2cc3301>`
  - Kernel: MMC Highspeed tuning and Performance Improvements
  - U-Boot: A53 SPL Splash Screen support - :ref:`A53 SPL Splash Overview <Uboot-splash-label>`
  - RT Kernel : Significant Improvements to Real-Time Linux Interrupt Latency - :ref:`RT Interrupt Latencies <RT-linux-performance>`
  - Power Management: DeepSleep, MCU-Only and Partial IO mode - :ref:`Power Management Overview <Power-Management>`
  - OOB: GPU Accelerated Chromium Browser Support - :ref:`Chromium Browser <Chromium_Browser-label>`
  - PM: MCU Only mode and Partial I/O mode
  - TIFS, DM, R5 SPL: PLL Configuration sequence updated to latest recommendation
  - TISCI ABI version updated to 4.0 from 3.1 (Low power mode related API changes)

**Component version:**

  - Kernel 6.6.32
  - RT Kernel 6.6.32-rt32
  - U-Boot 2024.04
  - Toolchain GCC 13.3
  - ATF 2.10+
  - OPTEE 4.2.0
  - Graphics DDK 24.1
  - TIFS Firmware v10.00.08
  - DM Firmware 10.00.00.08
  - Yocto scarthgap

Build Information
=================

.. _u-boot-release-notes:

U-Boot
------

.. rubric:: u-boot
   :name: u-boot

| Head Commit: fda88f8bcea30590528930ff9441c6e958da86f5 clk: ti: clk-k3-pll: Add additional robustness steps to the PLL sequence
| Date: 2024-07-28 10:37:17 -0500
| uBoot Version: 2024.04
| uBoot Description: RC Release 10.00.07
| Clone: git://git.ti.com/ti-u-boot/ti-u-boot.git
| Branch: ti-u-boot-2024.04
| uBoot Tag: 10.00.07
|

.. _tf-a-release-notes:

TF-A
----
| Head Commit: 00f1ec6b8740ccd403e641131e294aabacf2a48b Merge changes from topic "revert-ti-dm-workaround" into integration
| Repo: https://git.trustedfirmware.org/TF-A/trusted-firmware-a.git
| Branch: master
| Tag: 2.10+
|

.. _optee-release-notes:

OP-TEE
------
| Head Commit: 12d7c4ee4642d2d761e39fbcf21a06fb77141dea Update CHANGELOG for 4.2.0
| Repo: https://github.com/OP-TEE/optee_os/
| Branch: master
| Tag: 4.2.0
|

.. _ti-linux-fw-release-notes:

ti-linux-firmware
-----------------
| Head Commit: 1e01062a34b88427c2fca1ce7c5a5c308961e0c7 ti-eth: update firmware to 10.00.00.02 for j721e, j7200 and j784s4
| Date: 2024-07-28 10:37:11 -0500
| Clone: https://git.ti.com/cgit/processor-firmware/ti-linux-firmware
| Branch: ti-linux-firmware
| Tag: 10.00.07
|

Kernel
------

.. rubric:: Linux Kernel
   :name: linux-kernel

| Head Commit: 6de6e418c80edfbe08f4a5f851c721bd60c0123b net: ti: icssg_prueth: Enable 10M Link issue quirk for AM64x
| Date: 2024-07-28 10:37:02 -0500
| Kernel Version: 6.6.32
| Kernel Description: RC Release 10.00.07

| Repo: git://git.ti.com/ti-linux-kernel/ti-linux-kernel.git
| Branch: ti-linux-6.6.y
| Tag: 10.00.07
| use-kernel-config=defconfig
| config-fragment=kernel/configs/ti_arm64_prune.config
|


.. rubric:: Real Time (RT) Linux Kernel
   :name: real-time-rt-linux-kernel

| Head Commit: 04a9ad081f0f255a046f398abf6faf1d4374267f Merge branch 'ti-linux-6.6.y-cicd' into ti-rt-linux-6.6.y-cicd
| Date: 2024-07-28 10:37:05 -0500
| Kernel Version: 6.6.32-rt32
| Kernel Description: RC Release 10.00.07-rt

| Repo: git://git.ti.com/ti-linux-kernel/ti-linux-kernel.git
| Branch: ti-rt-linux-6.6.y
| Tag: 10.00.07-rt
| use-kernel-config=defconfig
| config-fragment=config-fragment=kernel/configs/ti_arm64_prune.config kernel/configs/ti_rt.config
|

Yocto
-----
.. rubric:: meta-ti
   :name: meta-ti

| Head Commit: 138077349667614f83637c98798c06249615a23e CI/CD Auto-Merger: cicd.scarthgap.202407271443
| Date: 2024-07-28 10:37:17 -0500

| Clone: git://git.yoctoproject.org/meta-ti
| Branch: scarthgap
| Release Tag: 10.00.07
|

.. rubric:: meta-arago
   :name: meta-arago

| Head Commit: 82833bae8835e06301c23c8833642ae4c02d303a packagegroup-arago-tisdk-multimedia: Add ffmpeg package
| Date: 2024-07-28 10:36:40 -0500

| Clone: git://git.yoctoproject.org/meta-arago
| Branch: scarthgap
| Release Tag: 10.00.07
|

.. rubric:: meta-tisdk
   :name: meta-tisdk

| Head Commit: af81e0d81c5efd005bfc0ef749f690f9748c70f6 recipes-demos: ti-apps-launcher: Bump up SRCREV
| Date: 2024-08-05 01:53:23 -0500

| Clone: https://github.com/TexasInstruments/meta-tisdk.git
| Branch: scarthgap
| Release Tag: 10.00.07.04
|

.. rubric:: meta-edgeai
   :name: meta-edgeai

| Head Commit: 836b1a3aa89d087474495ab4f77fc7a06ffcef0f edgeai-test-data.bb: edgeai-tidl-models.bb: Updated EDGEAI_SDK_VERSION
| Date: 2024-07-30 05:58:20 -0500

| Clone: https://git.ti.com/git/edgeai/meta-edgeai.git
| Branch: scarthgap
| Release Tag: 10.00.00.04
|


Issues Tracker
==============

Errata Workarounds Available in this Release
------------------------------------------------
.. csv-table::
   :header: "Record ID", "Title", "Platform"
   :widths: 15, 30, 55

   "LCPD-37965","BCDMA: RX Channel can lockup in certain scenarios","am62axx_sk-fs,am62axx_sk-se,am62pxx_sk-fs,am62pxx_sk-se,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_p0_sk-fs,am62xx_sk-fs,am62xx_sk-se,am62xxsip_sk-fs,am62xxsip_sk-se"
   "LCPD-37081","SNPS: USB2 PHY locks up due to short suspend","am62axx_sk-fs,am62pxx_sk-fs,am62xx_lp_sk-fs,am62xxsip_sk-fs"

|

.. _known-issues:

Known Issues
------------
.. csv-table::
   :header: "Record ID", "Title", "Platform", "Workaround"
   :widths: 5, 10, 70, 35

   "LCPD-38696","Wave5: Seek issue with video playback","am62pxx_sk-fs",""
   "LCPD-38689","Linux benchmarks: add context to Boot-time measurement","am62axx_sk-fs,am62pxx_sk-fs,am62xx_lp_sk-fs,am64xx-evm,am654x-evm",""
   "LCPD-38688","RT Linux benchmarks: add histogram for cyclic test","am62axx_sk-fs,am62pxx_sk-fs,am62xx_lp_sk-fs,am62xx_sk-fs,am64xx-evm",""
   "LCPD-38672","SD Card / rootfs unmounts randomly after Deep Sleep suspend/resume cycle (AM62P)","am62pxx_sk-fs",""
   "LCPD-38665","AM62px: Verify IPC kernel: main-r5f0(s)/main-r5f1(s) fails to run","am62pxx_sk-fs",""
   "LCPD-38663","Verify IPC U-Boot/Kernel: main-r5f0 in split mode","am62pxx_sk-fs",""
   "LCPD-38662","rcu_preempt self-detected stall on CPU","am62axx_sk-fs,am62pxx_sk-fs,am62xx_lp_sk-fs,am62xx_sk-fs,am62xxsip_sk-fs,j721e-idk-gw,j721s2-evm",""
   "LCPD-38619","Documentation: kernel:  Update How_to_Check_Device_Tree_Info section","am62axx_sk-fs,am62axx_sk-se,am62pxx_sk-fs,am62pxx_sk-se,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_sk-fs,am62xx_sk-se,am62xxsip_sk-fs,am62xxsip_sk-se,am64xx-evm,beagleplay-gp",""
   "LCPD-38528","Documentation: IPC:  Update 6.1.y links to 6.6.y","am62pxx_sk-fs,am62xx_sk-fs,j722s_evm-fs",""
   "LCPD-38525","U-Boot packages Encryption key (custMpk.key) as replica of the Signing key (custMpk.pem)","am62pxx_sk-se,am62xx_lp_sk-se,am62xx_sk-se,am64xx-evm,am64xx-hsevm",""
   "LCPD-38254","Watchdog reset not functional: ESM pins are wrong","am62axx_sk-fs,am62pxx_sk-fs,am64xx-hsevm",""
   "LCPD-38252","Remove warning about graceful shutdown not supported","am62axx_sk-fs,am62pxx_sk-fs,am62xx_sk-fs,am64xx-evm",""
   "LCPD-38139","Watchdog fails to reset chip when counter reaches 0","am62axx_sk-fs,am62pxx_sk-fs,am64xx-evm,am64xx_sk-fs",""
   "LCPD-38074","Add Timer PWM documentation and other infrastructure as needed","am62axx_sk-fs,am62pxx_sk-fs,am62xx_lp_sk-fs,am62xx_sk-fs",""
   "LCPD-38040","mailbox tests marked as passing, but seem to actually fail","am62axx_sk-fs,am62pxx_sk-fs,am62xx_lp_sk-fs,am64xx-evm",""
   "LCPD-38039","Spinlock tests marked as passing, but seem to actually fail","am62axx_sk-fs,am62pxx_sk-fs,am62xx_lp_sk-fs,am64xx-evm",""
   "LCPD-38022","dhcp error for uart + nfs boot ","am62pxx_sk-fs",""
   "LCPD-38005","GPMC NAND driver runtime_pm support","am62axx_sk-fs,am62axx_sk-se,am62pxx_sk-fs,am62pxx_sk-se,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_sk-fs,am62xx_sk-se",""
   "LCPD-38004","serial NAND driver runtime_pm support","am62axx_sk-fs,am62axx_sk-se,am62pxx_sk-fs,am62pxx_sk-se,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_sk-fs,am62xx_sk-se",""
   "LCPD-37920","ti-rpmsg-char should use the same toolchain as current Yocto build","am335x-evm,am335x-ice,am335x-sk,am437x-idk,am437x-sk,am43xx-gpevm,am571x-idk,am572x-idk,am574x-idk,am57xx-evm,am62axx_sk-fs,am62pxx_sk-fs,am62xx_lp_sk-fs,am62xx_sk-fs,am64xx-evm,am64xx_sk-fs,am654x-idk",""
   "LCPD-37828","SPL: Use speedgrade info to choose the A53 clock values","am62axx_sk-fs,am62pxx_sk-fs,am62xx_sk-fs",""
   "LCPD-37750","SDK Documentation: Formatting: Spacing between Lines seems broken","am62axx_sk-fs,am62axx_sk-se,am62pxx_sk-fs,am62pxx_sk-se,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xxsip_sk-fs,am62xxsip_sk-se",""
   "LCPD-37467","AM62P low performance memory benchmark","am62pxx_sk-fs",""
   "LCPD-37342","cpufreq: schedutil: constant switch between CPU OPPs","am62axx_sk-fs,am62pxx_sk-fs,am62xx_lp_sk-fs,am62xx_sk-fs",""
   "LCPD-37226","Update Ubuntu Host version in Linux documentation","am335x-evm,am335x-hsevm,am335x-ice,am335x-sk,am437x-idk,am437x-sk,am43xx-gpevm,am43xx-hsevm,am571x-idk,am572x-idk,am574x-hsidk,am574x-idk,am57xx-beagle-x15,am57xx-evm,am57xx-hsevm,am62axx_sk-fs,am62axx_sk-se,am62lxx_evm-fs,am62lxx_evm-se,am62pxx_sk-fs,am62pxx_sk-se,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_sk-fs,am62xx_sk-se,am62xxsip_sk-fs,am62xxsip_sk-se,am64xx-evm,am64xx-hsevm,am64xx-hssk,am654x-evm,am654x-hsevm,am654x-idk,beagleplay-gp",""
   "LCPD-37210","MMC driver runtime_pm support","am62axx_sk-fs,am62axx_sk-se,am62pxx_sk-fs,am62pxx_sk-se,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_sk-fs,am62xx_sk-se",""
   "LCPD-36993","U-Boot: lpddr4.c: Error handling missing failure cases","am62axx_sk-fs,am62axx_sk-se,am62lxx-vlab,am62lxx-zebu,am62lxx_evm-fs,am62lxx_evm-se,am62pxx-zebu,am62pxx_sk-fs,am62pxx_sk-se,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_p0_sk-fs,am62xx_sk-fs,am62xx_sk-se,am62xxsip_sk-fs,am62xxsip_sk-se,am64xx-evm,am64xx-hsevm,am64xx-hssk,am64xx_evm-se,am64xx_sk-fs,am64xx_sk-se,am654x-evm,am654x-hsevm,am654x-idk,am68_sk-fs,am69_sk-fs,bbai,bbai64-gp,beaglebone,beagleplay-gp,j7200-evm,j7200-hsevm,j721e-evm-ivi,j721e-hsevm,j721e-idk-gw,j721e-sk,j721s2-evm,j721s2-hsevm,j721s2_evm-fs,j721s2_evm-se,j722s_evm-fs,j784s4-evm,j784s4-hsevm",""
   "LCPD-36950","crypto openssl performance test fail","am62axx_sk-fs,am62pxx_sk-fs,am62xx_sk-fs",""
   "LCPD-34926","Some LTP tests are failing due to missing configurations","am62axx_sk-fs,am62pxx_sk-fs,am62xx_sk-fs,am64xx-hsevm,j7200-evm",""
   "LCPD-32931","OSPI: Update PHY tuning algorithm for PHY Tuning limitations","am62axx_sk-fs,am62axx_sk-se,am62pxx_sk-fs,am62pxx_sk-se,am62xx-lp-sk,am62xx-sk,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_sk-fs,am62xx_sk-se,am64xx-evm,am64xx-hsevm,am64xx-hssk,am64xx_sk-fs,am68_sk-fs,am69_sk-fs,j7200-evm,j7200-hsevm,j721e-hsevm,j721e-idk-gw,j721e-sk,j721s2-evm,j721s2-hsevm,j721s2_evm-fs,j784s4-evm,j784s4-hsevm","Forced Half-Cycle DLL Lock Mode, 100MHz - 166MHz only (100MHz is a Master Mode DLL limitation) Full tuning range of 0-127 should be the default for both RX and TX"
   "LCPD-29409","DMIPS number should reflect all 4 cores","am62pxx_sk-fs,am62pxx_sk-se,am62xx-sk,am62xx_sk-fs,am62xx_sk-se,j721e-idk-gw,j721s2-evm",""
   "SYSFW-5992","Unable to set exact pixel clock for OLDI LCD display / HDMI Pixel clock","am62x, am62a, am62px",""
   "SYSFW-6369","DM unable to enter deep sleep mode when booting in SBL flow","am62x, am62a, am62px",""
   "SYSFW-6432","Set device API doesn't return Error when PD is in transition state","am62x,am62ax,am62px,am64x,am65x",""
   "SYSFW-6426","Ownership of a firewall region can be transferred to an invalid host","am62x,am62ax,am62px,am64x,am65x",""
   "SYSFW-7559","LPM: In MCU Only mode resume path the MCU_M4 LPSC is ON","am62x,am62ax,am62px",""
   "SYSFW-7571","LPM: Device IDs higher than 255 will not work with set device constraint","am62x,am62ax,am62px",""
   "SITSW-4773","DM is not receiving the exact flags passed by sender for all K3 devices","am62x,am62ax,am62px",""
   "SITSW-3922","Flash writer: Benchmark script fails for emmc logs","am62x,am62ax,am62px,am64x",""
   "SITSW-5048","AM62P: ti-img-rogue kernel driver makefile bug","am62px",""
   "SITSW-5041","Debian: LPM not working again on AM62P, AM62LP and AM62SIP","am62p-sk,am62xx-sk-lp,am62x-sip-sk",""
   "SITSW-5049","Debian: Chromium doesn't display minimize and maximize buttons","am62p-sk,am62xx-sk,am62xx-sk-lp",""
   "SITSW-4864","TI Debian SDK: Docker not working","am62xx-sk,am62xx-sk-lp,am62x-sip-sk,am62p-sk,am64xx-evm,am64xx-sk",""

|

Closed Issues in Current Release
--------------------------------

.. csv-table::
   :header: "Record ID", "Title", "Platform"
   :widths: 15, 70, 25

   "LCPD-38691","Documentation: Remove external links of Kernel 5.10/ 6.1 &/or U-Boot 2023.04","am62pxx_sk-fs,am62xx-evm,am64xx-evm,am654x-evm"
   "LCPD-38685","Documentation: U-Boot: Update doc references to 2024.04","am62pxx_sk-fs,am62xx_lp_sk-fs,am62xx_sk-fs"
   "LCPD-38532","Documentation: U-Boot: Update DDR doc references to 2024.04","am62pxx_sk-fs,am62xx_lp_sk-fs,am62xx_sk-fs"
   "LCPD-38531","Documentation: Splash: Update doc to U-Boot 2024.04","am62pxx_sk-fs,am62xx_lp_sk-fs,am62xx_sk-fs"
   "LCPD-38529","Documentation: PM: Update Docs for 10.00","am62axx_sk-fs,am62pxx_sk-fs,am62xx_sk-fs"
   "LCPD-38372","FPDLink: RX Port skipping leads to corrupt VC","am62axx_sk-fs,am62axx_sk-se,am62pxx_sk-fs,am62pxx_sk-se,j7200-evm,j721e-idk-gw,j721e-sk,j721s2-evm,j721s2_evm-fs,j722s_evm-fs,j784s4-evm"
   "LCPD-38358","AM62P: Error: ""boot_rprocs"" not defined","am62pxx_sk-fs,am62pxx_sk-se"
   "LCPD-38353","fitImage boot fails on HS-FS Platforms","am62pxx_sk-fs,am62pxx_sk-se,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_sk-fs,am62xx_sk-se,am62xxsip_sk-fs,am62xxsip_sk-se,am64xx_sk-fs,am64xx_sk-se,beagleplay-gp"
   "LCPD-38305","tiL_6.6: OSPI NOR: UBIFS test fail","am62pxx_sk-fs,am62xx_sk-fs"
   "LCPD-38265","tiU_24.4: OSPI NOR Read taking more time","am62pxx_sk-fs,am62xx_sk-fs,am64xx_sk-fs"
   "LCPD-38239","AM62xx: Board doesn't resume from deepsleep","am62pxx_sk-fs,am62xx_sk-fs"
   "LCPD-38180","SK-AM62x: OSPI: spi-nor resume fails with error -22","am62pxx_sk-fs,am62xx_sk-fs"
   "LCPD-38163","RPMSG IPC error upon power cycling the board.","am62pxx_sk-fs,am62pxx_sk-se"
   "LCPD-38098","IPC failure in LTS 2024","am62axx_sk-fs,am62axx_sk-se,am62lxx-vlab,am62lxx-zebu,am62lxx_evm-fs,am62lxx_evm-se,am62pxx-zebu,am62pxx_sk-fs,am62pxx_sk-se,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_p0_sk-fs,am62xx_sk-fs,am62xx_sk-se,am62xxsip_sk-fs,am62xxsip_sk-se,am64xx-evm,am64xx-hsevm,am64xx-hssk,am64xx_evm-se,am64xx_sk-fs,am64xx_sk-se,am654x-evm,am654x-hsevm,am654x-idk,am68_sk-fs,am68_sk-se,am69_sk-fs,j7200-evm,j7200-hsevm,j721e-evm-ivi,j721e-hsevm,j721e-idk-gw,j721e-sk,j721s2-evm,j721s2-hsevm,j721s2_evm-fs,j721s2_evm-se,j722s_evm-fs,j784s4-evm,j784s4-hsevm"
   "LCPD-38038","6.6.30 : Build Regression on K3 platforms due to kselftest","am335x-evm,am437x-idk,am57xx-evm,am62axx_sk-fs,am62pxx_sk-fs,am62xx_sk-fs,am62xxsip_sk-fs,am64xx-hsevm,am654x-idk,am68_sk-fs,am69_sk-fs"
   "LCPD-38001","Doc: Uboot build instructions need to document specific python dependencies for binman","am62axx_sk-fs,am62pxx_sk-fs,am62xx_lp_sk-fs,am62xx_sk-fs,am62xxsip_sk-fs,am64xx-hsevm,j7200-evm,j721e-idk-gw,j721s2-evm,j721s2_evm-fs,j722s_evm-fs,j784s4-evm"
   "LCPD-37898","watchdog documentation should explain how to set timeout","am335x-evm,am335x-ice,am335x-sk,am437x-idk,am437x-sk,am43xx-gpevm,am62axx_sk-fs,am62pxx_sk-fs,am62xx_sk-fs,am64xx-evm,am64xx_sk-fs,am654x-evm,am654x-idk"
   "LCPD-37875","U-boot: otapdly and otap_del_sel do not get written to PHY CTRL 4 reg","am62pxx_sk-fs,am62pxx_sk-se,am62xx-sk,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_sk-fs,am62xx_sk-se,am62xxsip_sk-fs,am62xxsip_sk-se,am64xx-evm,am64xx-hsevm,am64xx-hssk,am64xx_evm-se,am64xx_sk-fs,am64xx_sk-se"
   "LCPD-37825","AM62P: Speed grade `O` not handled in cpufreq driver","am62pxx_sk-fs"
   "LCPD-37714","CAN suspend and loopback tests are failing","am62axx_sk-fs,am62axx_sk-se,am62pxx_sk-fs,am62pxx_sk-se,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_sk-fs,am62xx_sk-se,am62xxsip_sk-fs,am62xxsip_sk-se,am64xx-evm,am64xx-hsevm,am64xx-hssk"
   "LCPD-37320","AM62P: AM62A: update OPP speed grade decoding","am62axx_sk-fs,am62axx_sk-se,am62pxx_sk-fs,am62pxx_sk-se"
   "LCPD-37141","AM62x: Sync up USB R5 defconfigs with main R5 defconfig","am62axx_sk-fs,am62pxx_sk-fs,am62xx_lp_sk-fs,am62xx_sk-fs"
   "LCPD-32250","Doc: Linux driver for eQEP","am62axx_sk-fs,am62axx_sk-se,am62pxx_sk-fs,am62pxx_sk-se,am62xx_lp_sk-fs,am62xx_lp_sk-se,am62xx_p0_sk-fs,am62xx_sk-fs,am62xx_sk-se,am62xxsip_sk-fs,am62xxsip_sk-se,am64xx-hssk,am64xx_sk-fs,am64xx_sk-se"
   "LCPD-38690","Documentation: Remove reference of denx.de/wiki","am62pxx_sk-fs,am62pxx_sk-se,am62xx-evm,am62xx-lp-sk,am62xx-sk,am62xx_lp_sk-fs,am62xxsip_sk-fs,am62xxsip_sk-se,am64xx-evm"
   "SYSFW-7536","Sending JTAG unlock certificate to TIFS using T32 JTAG fails","am62x,am62ax,am62px,am64x,am65x"
   "SYSFW-7474","Write access from DMA initiators to RA GCFG region results in firewall exception","am62x,am62ax,am62px"
   "SYSFW-7463","TISCI_MSG_GET_CLOCK always return Enabled for input clock","am62x,am62ax,am62px,am64x,am65x"
   "SYSFW-7485","Update the PLL driver in TIFS boot flow to follow correct sequence","am62x,am62ax,am62px,am64x,am65x"
   "SYSFW-7486","PM: Cleanup additional steps in pll init startup routine","am62x,am62ax,am62px,am64x,am65x"
   "SITSW-4481","Debian SDK documentation misses instructions for building kernel package","am62x-sk,am62p-sk,am64xx-evm,am64xx-sk,am62xx-sk-lp,am62x-sip-sk"
   "SITSW-4288","Debian: Dual-display doesn't work out-of-box","am62xx-sk,am62p-sk,am62xx-sk-lp,am62x-sip-sk"
   "SITSW-5040","TI Debian SDK: Build instructions no longer working due to ti-bdebstrap Advancement","am62xx-sk,am62xx-sk-lp,am62x-sip-sk,am62p-sk,am64xx-evm,am64xx-sk"

|

