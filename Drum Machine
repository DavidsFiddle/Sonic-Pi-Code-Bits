#Drum Machine
#Coded by Davids Fiddle

#How to use:
#amp_x sets the volume of the piece, use 0 to turn the piece off
#also keep the values under 5 to avoid compression and clipping
#
#trigger_x is a ring that has 1 for 'hit' and 0 for 'dont'
#2 is used for 'soft' hits, except for the hihat
#
#unit_x controls the note length

#This is Measures / Minute, not Beats
use_bpm 25 # 4/4 with 120BPM => a value of 30

whole = 1
dotted_half = 0.75
half = 0.5
dotted_quarter = 0.375
quarter = 0.25
eighth = 0.125
sixteenth = 0.0625


#Controls the metronome
amp_blip = 0
unit_blip = quarter
note_blip = :g6

#Controls the kickdrum
amp_kik = 1
trigger_kik = [1,0,1,0].ring
unit_kik = quarter

#Controls the snare
amp_snare = 1
trigger_snare = [0,1,0,1].ring
unit_snare = quarter

#Controls the hihat
amp_hihat = 1.5
trigger_hihat = [5,5,5,5,5,5,5,5].ring
# 1...5 <=> hard, soft, pedal, open, closed
unit_hihat = eighth

#Controls the low tom
amp_tomlo = 0
trigger_tomlo = [0,0,1,0,0,0,0,0].ring
unit_tomlo = eighth

#Controls the mid tom
amp_tommid = 0
trigger_tommid = [0,1,0,0].ring
unit_tommid = quarter

#Controls the hi tom
amp_tomhi = 0
trigger_tomhi = [0,1,0,0,0,0,0,0].ring
unit_tomhi = eighth

#Code starts here!
live_loop :blip do
  play note_blip, attack: 0, decay: 0, sustain: 0, release: 0.125, amp: amp_blip
  sleep unit_blip
end

live_loop :kik do
  tick
  sample :drum_bass_hard, amp: amp_kik if trigger_kik.look == 1
  sample :drum_bass_soft, amp: amp_kik if trigger_kik.look == 2
  sleep unit_kik
end

live_loop :snare do
  tick
  sample :drum_snare_hard, amp: amp_snare if trigger_snare.look == 1
  sample :drum_snare_soft, amp: amp_snare if trigger_snare.look == 2
  sleep unit_snare
end

live_loop :hihat do
  tick
  sample :drum_cymbal_hard, amp: amp_hihat if trigger_hihat.look == 1
  sample :drum_cymbal_soft, amp: amp_hihat if trigger_hihat.look == 2
  sample :drum_cymbal_pedal, amp: amp_hihat if trigger_hihat.look == 3
  sample :drum_cymbal_open, amp: amp_hihat if trigger_hihat.look == 4
  sample :drum_cymbal_closed, amp: amp_hihat if trigger_hihat.look == 5
  sleep unit_hihat
end

live_loop :tomhi do
  tick
  sample :drum_tom_hi_hard, amp: amp_tomhi if trigger_tomhi.look == 1
  sample :drum_tom_hi_soft, amp: amp_tomhi if trigger_tomhi.look == 2
  sleep unit_tomhi
end

live_loop :tomlo do
  tick
  sample :drum_tom_lo_hard, amp: amp_tomlo if trigger_tomlo.look == 1
  sample :drum_tom_lo_soft, amp: amp_tomlo if trigger_tomlo.look == 2
  sleep unit_tomlo
end


live_loop :tommid do
  tick
  sample :drum_tom_mid_hard, amp: amp_tommid if trigger_tommid.look == 1
  sample :drum_tom_mid_soft, amp: amp_tommid if trigger_tommid.look == 2
  sleep unit_tommid
end
