# confdb_v2.xml_To_OAI_conf
online calculator: https://dustinchen26.github.io/confdb_v2.xml_To_OAI_conf

## Example
```
confdb_v2_Cedar_n78.xml
confdb_v2_Sharp_n79.xml
【Input】Upload or Paste confdb_v2.xml (底下上傳confdb_v2_Sharp_n79.xml)
...
            <RF>
              <NRARFCNDL>723324</NRARFCNDL>
              <PhyCellID>30</PhyCellID>
              <DLBandwidth>100</DLBandwidth>
              <ULBandwidth>100</ULBandwidth>
              <PSCHPowerOffset>db0</PSCHPowerOffset>
              <NRARFCNUL>723324</NRARFCNUL>
              <FreqBandIndicator>79</FreqBandIndicator>
              <SsPBCHBlockPower>-35</SsPBCHBlockPower>
              <ForgetFactorRbNoise>8</ForgetFactorRbNoise>
              <SsbFrequency xsi:nil="true"/>
              <gNBDUId xsi:nil="true"/>
              <DigitalBeamFormingMode>false</DigitalBeamFormingMode>
              <AnalogBeamformingMode>false</AnalogBeamformingMode>
              <BandwidthAutoConfig>false</BandwidthAutoConfig>
            </RF>
            <PHY>
              <FrequencyInfoDLSIB>
                <OffsetToPointA>5</OffsetToPointA>
                <MultiFrequencyBandListNRSIB id="1">
                  <FreqBandIndicatorNR>12</FreqBandIndicatorNR>
                </MultiFrequencyBandListNRSIB>
                <ScsSpecificCarrierList id="1">
                  <SCSSpecificCarrier>
                    <OffsetToCarrier>0</OffsetToCarrier>
                    <SubcarrierSpacing>1</SubcarrierSpacing>
                    <CarrierBandwidth>273</CarrierBandwidth>
                  </SCSSpecificCarrier>
                </ScsSpecificCarrierList>
              </FrequencyInfoDLSIB>
              <FrequencyInfoULSIB>
                <AbsoluteFrequencyPointA>720048</AbsoluteFrequencyPointA>
                <ScsSpecificCarrierList id="1">
                  <SCSSpecificCarrier>
                    <OffsetToCarrier>0</OffsetToCarrier>
                    <SubcarrierSpacing>1</SubcarrierSpacing>
                    <CarrierBandwidth>273</CarrierBandwidth>
                  </SCSSpecificCarrier>
                </ScsSpecificCarrierList>
                <IsPMaxPresent>true</IsPMaxPresent>
                <Pmax>23</Pmax>
              </FrequencyInfoULSIB>
              <SSB>
                <SsbPositionsInBurst>
                  <InOneGroup>8</InOneGroup>
                </SsbPositionsInBurst>
                <SsbPeriodicityServingCell>3</SsbPeriodicityServingCell>
                <SsPBCHBlockPower>-36</SsPBCHBlockPower>
                <SsbSubcarrierOffset>9</SsbSubcarrierOffset>
              </SSB>
              <SubCarrierSpacingCommon>scs30or120</SubCarrierSpacingCommon>
              <TddULDLConfigurationCommon>
                <ReferenceSubcarrierSpacing>1</ReferenceSubcarrierSpacing>
                <IsPattern2Present>true</IsPattern2Present>
                <pattern1>
                  <DlULTransmissionPeriodicity>8</DlULTransmissionPeriodicity>
                  <NrofDownlinkSlots>3</NrofDownlinkSlots>
                  <NrofDownlinkSymbols>6</NrofDownlinkSymbols>
                  <NrofUplinkSlots>2</NrofUplinkSlots>
                  <NrofUplinkSymbols>4</NrofUplinkSymbols>
                </pattern1>
                <pattern2>
                  <DlULTransmissionPeriodicity>4</DlULTransmissionPeriodicity>
                  <NrofDownlinkSlots>4</NrofDownlinkSlots>
                  <NrofDownlinkSymbols>0</NrofDownlinkSymbols>
                  <NrofUplinkSlots>0</NrofUplinkSlots>
                  <NrofUplinkSymbols>0</NrofUplinkSymbols>
                </pattern2>
			
【Output】OAI conf
# OAI配置文件 - 文件2配置
# 生成時間: 2025-11-28T00:04:34.190Z
# 源參數: NRARFCNDL=723324, PhyCellID=30, 頻段=79

Active_gNBs = ( "du-rfsim");
# Asn1_verbosity, choice in: none, info, annoying
Asn1_verbosity = "none";

gNBs =
(
 {
    ////////// Identification parameters:
    gNB_ID = 0xe00;
    gNB_DU_ID = 0xe00;
    gNB_name  =  "du-rfsim";

    // Tracking area code, 0x0000 and 0xfffe are reserved values
    tracking_area_code  =  1;
    plmn_list = ({ mcc = 001; mnc = 01; mnc_length = 2; snssaiList = ({ sst = 1; }) });

    nr_cellid = 647169L;

    ////////// Physical parameters:

    min_rxtxtime = 6;

    servingCellConfigCommon = (
    {
 #spCellConfigCommon

      physCellId                                               = 30;

#  downlinkConfigCommon
    #frequencyInfoDL
      # this is the SSB frequency
      absoluteFrequencySSB                                      = 720288;
      dl_frequencyBand                                          = 79;
      # this is the Point A frequency
      dl_absoluteFrequencyPointA                                = 720048;
      #scs-SpecificCarrierList
        dl_offstToCarrier                                       = 0;
# subcarrierSpacing
# 0=kHz15, 1=kHz30, 2=kHz60, 3=kHz120
        dl_subcarrierSpacing                                    = 1;
        dl_carrierBandwidth                                     = 273;
     #initialDownlinkBWP
      #genericParameters
        # this is RBstart=27,L=48 (275*(L-1))+RBstart
        initialDLBWPlocationAndBandwidth                         = 1099;
# subcarrierSpacing
# 0=kHz15, 1=kHz30, 2=kHz60, 3=kHz120
        initialDLBWPsubcarrierSpacing                             = 1;
      #pdcch-ConfigCommon
        initialDLBWPcontrolResourceSetZero                        = 4;
        initialDLBWPsearchSpaceZero                               = 0;

  #uplinkConfigCommon
     #frequencyInfoUL
      ul_frequencyBand                                             = 79;
      #scs-SpecificCarrierList
      ul_offstToCarrier                                            = 0;
# subcarrierSpacing
# 0=kHz15, 1=kHz30, 2=kHz60, 3=kHz120
      ul_subcarrierSpacing                                         = 1;
      ul_carrierBandwidth                                          = 273;
      pMax                                                         = 23;
     #initialUplinkBWP
      #genericParameters
        initialULBWPlocationAndBandwidth                           = 1099;
# subcarrierSpacing
# 0=kHz15, 1=kHz30, 2=kHz60, 3=kHz120
        initialULBWPsubcarrierSpacing                              = 1;
      #rach-ConfigCommon
        #rach-ConfigGeneric
          prach_ConfigurationIndex                                 = 198;
#prach_msg1_FDM
#0 = one, 1=two, 2=four, 3=eight
          prach_msg1_FDM                                           = 0;
          prach_msg1_FrequencyStart                                = 2;
          zeroCorrelationZoneConfig                                = 10;
          preambleReceivedTargetPower                              = -90;
#preamblTransMax (0...10) = (3,4,5,6,7,8,10,20,50,100,200)
          preambleTransMax                                         = 7;
#powerRampingStep
# 0=dB0,1=dB2,2=dB4,3=dB6
        powerRampingStep                                           = 2;
#ssb_perRACH_OccasionAndCB_PreamblesPerSSB_PR
#1=oneeighth,2=onefourth,3=half,4=one,5=two,6=four,7=eight,8=sixteen
        ssb_perRACH_OccasionAndCB_PreamblesPerSSB_PR               = 4;
#one (0..15) 4,8,12,16,...60,64
        ssb_perRACH_OccasionAndCB_PreamblesPerSSB                  = 7;
#ra_ContentionResolutionTimer
#(0..7) 8,16,24,32,40,48,56,64
        ra_ContentionResolutionTimer                               = 7;
        rsrp_ThresholdSSB                                          = 0;
#prach-RootSequenceIndex_PR
#1 = 839, 2 = 139
        prach_RootSequenceIndex_PR                                 = 2;
        prach_RootSequenceIndex                                    = 1;
        # SCS for msg1, can only be 15 for 30 kHz < 6 GHz, takes precendence over the one derived from prach-ConfigIndex
        #
        msg1_SubcarrierSpacing                                     = 1,
# restrictedSetConfig
# 0=unrestricted, 1=restricted type A, 2=restricted type B
        restrictedSetConfig                                        = 0,

        msg3_DeltaPreamble                                         = 0;
        p0_NominalWithGrant                                        = -78;
        #msg3_Alpha                                                 = alpha1;

# pucch-ConfigCommon setup :
# pucchGroupHopping
# 0 = neither, 1= group hopping, 2=sequence hopping
        pucchGroupHopping                                          = 0;
        hoppingId                                                  = 40;
        p0_nominal                                                 = -96;

      ssb_PositionsInBurst_Bitmap                                  = 128;

# ssb_periodicityServingCell
# 0 = ms5, 1=ms10, 2=ms20, 3=ms40, 4=ms80, 5=ms160, 6=spare2, 7=spare1
      ssb_periodicityServingCell                                   = 2;

# dmrs_TypeA_position
# 0 = pos2, 1 = pos3
      dmrs_TypeA_Position                                           = 0;

# subcarrierSpacing
# 0=kHz15, 1=kHz30, 2=kHz60, 3=kHz120
      subcarrierSpacing                                            = 1;

  #tdd-UL-DL-ConfigurationCommon
# subcarrierSpacing
# 0=kHz15, 1=kHz30, 2=kHz60, 3=kHz120
      referenceSubcarrierSpacing                                   = 1;

      # pattern1
      # dl_UL_TransmissionPeriodicity
      # 0=ms0p5, 1=ms0p625, 2=ms1, 3=ms1p25, 4=ms2, 5=ms2p5, 6=ms5, 7=ms10
      # ext: 8=ms3, 9=ms4
      dl_UL_TransmissionPeriodicity                                = 8;
      nrofDownlinkSlots                                            = 3;
      nrofDownlinkSymbols                                          = 6;
      nrofUplinkSlots                                              = 2;
      nrofUplinkSymbols                                            = 4;

      # pattern2
      pattern2: {
        dl_UL_TransmissionPeriodicity2                             = 4;
        nrofDownlinkSlots2                                         = 4;
        nrofDownlinkSymbols2                                       = 0;
        nrofUplinkSlots2                                           = 0;
        nrofUplinkSymbols2                                         = 0;
      };

      ssPBCH_BlockPower                                            = -35;
     }

  );

    # ------- SCTP definitions
    SCTP :
    {
        # Number of streams to use in input/output
        SCTP_INSTREAMS  = 2;
        SCTP_OUTSTREAMS = 2;
    };
  }
);

MACRLCs = ({
    num_cc              = 1;
    tr_s_preference     = "local_L1";
    tr_n_preference     = "f1";
    local_n_address     = "127.0.0.4";
    remote_n_address    = "127.0.0.3";
    local_n_portd       = 2152;
    remote_n_portd      = 2152;
    pusch_FailureThres  = 1000;
    
    # MAC層參數
    sr_Period           = 40;
    layerOne_EntryMcs   = 11;
    layerOne_LeaveMcs   = 24;
    layerTwo_EntryMcs   = 14;
    layerTwo_LeaveMcs   = 13;
    
    # 聚合級別配置
    aggregation_Level4  = 2;
    aggregation_Level8  = 1;
    aggregation_Level16 = 0;
});

L1s = ({
    num_cc = 1;
    tr_n_preference = "local_mac";
    prach_dtx_threshold = 200;
    pucch0_dtx_threshold = 150;
    ofdm_offset_divisor = 8; #set this to UINT_MAX for offset 0
});

RUs = ({
    local_rf       = "yes"
    nb_tx          = 1
    nb_rx          = 1
    att_tx         = 0
    att_rx         = 0;
    bands          = [79];
    max_pdschReferenceSignalPower = -27;
    max_rxgain                    = 114;
    eNB_instances  = [0];
    clock_src = "internal";
});

rfsimulator: {
  serveraddr = "server";
  serverport = 4043;
  options = (); #("saviq"); or/and "chanmod"
  modelname = "AWGN";
  IQfile = "/tmp/rfsimulator.iqs"
}

log_config: {
  global_log_level = "info";
  hw_log_level     = "info";
  nr_phy_log_level = "info";
  nr_mac_log_level = "info";
  rlc_log_level    = "info";
  pdcch_log_level  = "info";
  rrc_log_level    = "info";
  f1ap_log_level   = "info";
  ngap_log_level   = "debug";
};

# 定時器配置
timer_config: {
  ue_inactive_timer = 300;
};

e2_agent = {
  near_ric_ip_addr = "127.0.0.1";
  sm_dir = "/usr/local/lib/flexric/"
};
```